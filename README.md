# diary-notes-html
个人练习，一个网页版个人日记便签库

这是一个基于 HTML、CSS 和 JavaScript 的本地日记和便签管理工具，旨在帮助用户记录和管理个人日记及便签。
项目支持日记和便签的导入、导出、新增、修改、删除功能，所有数据存储在浏览器的 `localStorage` 中，无需后端支持。
本项目为个人练习，所有代码和功能实现由 **Grok 3** 协助完成。
![效果图](https://raw.githubusercontent.com/shenyan21/diary-note-html/4ced66ef563e9312225a85a50a691ba57b3e56fe/diary%E6%95%88%E6%9E%9C%E5%9B%BE.png)
## 功能特性

- **日记展示**：展示日记列表，按时间倒序排列，显示标题、时间和内容预览。
- **便签展示**：展示便签列表，显示标题，点击查看详细信息。
- **添加、删除与编辑**：
  - 通过右下角“+”按钮添加新日记，支持标题、时间、内容和可选图片。
  - 通过便签区域的“新增便签”按钮添加便签，支持标题和内容。
  - 支持编辑和删除日记及便签。
- **背景图片自定义**：支持上传背景图片并调整透明度，设置保存在 `localStorage` 中。
- **导入与导出**：
  - 支持从 JSON 文件导入日记和便签数据。
  - 支持将日记和便签数据导出为 JSON 文件。
- **本地存储**：所有数据（日记、便签、背景设置）存储在浏览器 `localStorage`，无需服务器。
- **注意**：清除浏览器缓存会丢失数据，请定期导出 JSON 文件以备份。

## 快速开始

### 安装

1. 下载项目 zip 压缩包到本地 `diary-notes-html-main.zip`。
2. 解压缩后使用浏览器直接打开 `diary.html` 文件。
3. 手动添加开始使用。

### 使用说明

1. **浏览日记与便签**：
   - 打开页面后，左侧显示日记列表，按时间倒序排列，右侧显示便签列表。
   - 点击日记条目查看详情，包括标题、时间、内容和图片（若有）。
   - 点击便签条目查看标题和内容。
2. **新增日记**：
   - 点击右下角“+”按钮，弹出“新建日记”弹窗。
   - 填写标题、时间、内容和可选图片，点击“保存”。
3. **新增便签**：
   - 在便签区域点击“新增便签”按钮，填写标题和内容，点击“保存”。
4. **编辑与删除**：
   - 在日记或便签详情页，点击“修改”编辑内容，或点击“删除”移除记录。
5. **设置背景图片**：
   - 在日记区域点击“背景图片”按钮，上传图片并使用滑块调整透明度。
   - 点击“保存”存储设置，或点击“删除图片”移除背景。
6. **导入数据**：
   - 点击“导入日记”或“导入便签”，选择符合格式的 JSON 文件。
7. **导出数据**：
   - 点击“导出日记”或“导出便签”，生成 JSON 文件用于备份。
8. **注意事项**：
   - 图片数据以 DataURL 格式存储在 JSON 文件中，导出文件可能较大。
   - 定期导出 JSON 文件以防数据丢失。

## 注意事项

- **数据安全**：由于数据存储在 `localStorage`，清除浏览器缓存会导致数据丢失，建议定期导出 JSON 文件。
- **图片大小**：上传的日记图片和背景图片会转为 DataURL 存储，可能增加 `localStorage` 占用空间，建议使用较小的图片。
- **浏览器兼容性**：本项目在现代浏览器（Chrome、Firefox、Edge 等）上测试正常，建议使用最新版本浏览器。
- **文件路径**：背景图片上传功能使用 `FileReader` API，图片以 DataURL 存储，不依赖本地文件路径。

## 后续改进计划

- 添加日记和便签的搜索功能，支持按关键字筛选。
- 实现日记分类或标签功能，方便按主题管理。

## 数据格式

### 日记 JSON 格式
```json
[
  {
    "title": "日记标题",
    "dateTime": "2025-05-17T05:41",
    "content": "日记内容",
    "image": "data:image/png;base64,..." // 可选，图片的 DataURL
  },
  ...
]
```

### 便签 JSON 格式
```json
[
  {
    "title": "便签标题",
    "content": "便签内容"
  },
  ...
]
```

### 背景设置 JSON 格式（存储在 `localStorage` 的 `bgSettings`）
```json
{
  "image": "data:image/png;base64,...", // 背景图片的 DataURL
  "opacity": 0.8 // 透明度，0 到 1
}
```
