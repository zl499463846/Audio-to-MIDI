# 音频转MIDI转换器 / Audio to MIDI Converter

<div align="center">
  <img src="https://img.shields.io/badge/version-26.19.16-blue.svg" alt="Version 26.19.16">
  <img src="https://img.shields.io/badge/license-MIT-green.svg" alt="License MIT">
  <img src="https://img.shields.io/badge/Audio-MIDI-blue" alt="Audio to MIDI">
</div>

## 项目简介

一个**完全基于Web**的实时音频转MIDI工具，无需安装任何软件，**无需上传文件到服务器**，直接在浏览器本地运行。支持多种转换算法和参数调节，可以将音频文件通过快速傅里叶变换转为MIDI格式。

**开源协议：** MIT (可随意商用，欢迎传播)

## 文件夹说明

本项目包含三个版本，分别放在不同的文件夹中：

| 文件夹 | 文件夹名 | 说明 |
|--------|--------|------|
| **/正式版** | `Releases` | **带详细注释，代码可读性好，适合学习和二次开发** |
| **/测试版** | `Beta` | **DEBUG版本，不稳定** |
| **/压缩版** | `Releases.min` | **代码混淆压缩，体积最小，加载速度最快** |

如果仅仅只是用于转换MIDI的话，可以直接下载根目录下的index.html(压缩版)

或者[点击这里在线使用](https://zl499463846.github.io/Audio-to-MIDI/)直接访问index.html

## 转换效果试听

为了让您更直观地感受不同算法的差异，这里用一个CC0协议的音频作为示例，展示了原音频与默认参数下三种MIDI生成算法转换后通过MIDI播放器用正弦波音色回放的效果对比。

**测试音频来源**：https://www.aigei.com/item/gu_feng_ji_a_14.html

<table>
<tr>
<td align="center">

**原音频**

</td>
<td align="center">

**高音质算法**

</td>
<td align="center">

**平衡修复算法**

</td>
<td align="center">

**传统处理算法**

</td>
</tr>
<tr>
<td align="center">

原始音频文件，用于对照

</td>
<td align="center">

音质还原度高，文件较大，对播放器要求高

</td>
<td align="center">

在音质和兼容性之间取得平衡

</td>
<td align="center">

文件小，通用性高，类似于普通转换网站的效果

</td>
</tr>
<tr>
<td align="center">

<https://github.com/user-attachments/assets/73b0d2f3-d8a9-4cb7-b1f6-41c45d4a81df>

</td>
<td align="center">

<https://github.com/user-attachments/assets/55f3c3de-241c-401f-ad09-1cd7a2eba1cd>

</td>
<td align="center">

<https://github.com/user-attachments/assets/9a1e22ab-9f65-4e70-8488-aba250a8c0ca>

</td>
<td align="center">

<https://github.com/user-attachments/assets/b5f1ce5e-bc82-4177-853b-d3fc2a604ecf>

</td>
</tr>
</table>

> **请注意**：您听到的音频并非直接输出的MIDI文件，而是将生成的MIDI文件通过通用MIDI播放器回放并录制的结果，以便您直接聆听算法对音频信息的提取效果。


## 功能

- **实时FFT分析**：基于快速傅里叶变换
- **可调节参数**：
  - MIDI音符范围（0-127）
  - FFT大小（512-32768）
  - 重叠因子（2x-16x）
  - 响度阈值
  - 响度缩放
- **三种MIDI生成算法**：
  - 高音质算法（文件大，音质高，兼容性差）
  - 平衡修复算法（音质略差于高音质算法，兼容性一般）
  - 传统处理算法（文件小，兼容性高）
- **MIDI预览**：直接在浏览器中试听转换结果
- **实时统计**：显示帧数、音符数等信息

## 使用方法

1. **上传音频**：点击上传区域或拖拽音频文件
2. **调节参数**：根据需要调整转换参数
3. **开始转换**：点击"开始转换"按钮
4. **试听/下载**：预览效果后下载MIDI文件

## 参数说明

| 参数 | 说明 |
|------|------|
| **最低/最高MIDI音符** | 设置生成的MIDI音符范围 |
| **FFT重叠因子** | 越大时间分辨率越高，处理时间越长 |
| **响度阈值** | 阈值越小，音质越高，生成的MIDI体积越大 |
| **响度缩放** | 调节音符力度 |
| **FFT大小** | 512-32768，越小时间精度越高，文件越大 |
| **MIDI处理模式** | 三种算法可选 |

## 注意事项

- FFT大小设置为4096时音质最均衡
- 响度阈值默认0.005，可根据音频调整
- 处理大文件时请耐心等待，FFT算法较吃CPU
- 转换过程中不要多次点击按钮，避免闪退

## 常见问题

**Q: 转换后的MIDI听起来不像原音频？**
A: MIDI只包含音符信息，不包含音色。您需要在播放器中为MIDI分配合适的音色才能还原原声

**Q: 为什么转换速度很慢？**
A: FFT算法计算量大，处理长音频或高精度设置时需要更多时间，这是正常现象

**Q: 支持哪些音频格式？**
A: 浏览器支持的格式：MP3、WAV、OGG、M4A、FLAC、WMA、WEBM、WEBA、AU、AIFF、OPUS、OGA、MKA等

**Q: 可以批量转换吗？**
A: 不能，当前支持单个文件转换，批量转换功能正在开发中

## 参与贡献

欢迎各种形式的贡献！无论是提交bug报告、新功能建议，还是直接提交PR，我都会积极听取您宝贵的意见！

## 许可证

MIT License - 可随意商用，按理来说需要署名，但不署名我也不会追究任何责任，只是为了给自己留一条后路

免责声明：本项目为个人独立开发的开源学习项目，旨在探索Web Audio API与音频处理技术。我保证整个代码均为原创，代码的各个FEAT、FIX、BETA版本均有归档。如有雷同，纯属技术方案上的巧合。项目根据MIT协议开源，使用者需自行承担风险。

---

<div align="center">
   如果这个项目对您有帮助，欢迎Star！ 
</div>
