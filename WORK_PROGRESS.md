# 当前进度备份

任务：根据仓库中三本机械设计教材，主参考 `mechanical_design_textbook.pdf`，提取主教材第2章、第3章章节名，并与另外两本 `机械设计【西北工业大学，第十版】_濮良贵.pdf`、`机械设计（第四版）_邱宣怀.pdf` 对应内容匹配，生成适合零基础学习、公式印刷体、美观排版 PDF。

已确认：
- 远程仓库：`https://github.com/ohyeahkpn3-commits/pdf-store`
- 主参考：`mechanical_design_textbook.pdf`，344页
- 补充书1：`机械设计【西北工业大学，第十版】_濮良贵.pdf`，455页
- 补充书2：`机械设计（第四版）_邱宣怀.pdf`，478页
- 已 `git pull --ff-only` 拉到两本补充书
- `/tmp/pdf_review/main_ch2_ch3_ocr.txt` 有主教材第2、3章OCR文本
- `/tmp/pdf_review/chapters/pu/` 和 `/tmp/pdf_review/chapters/qiu/` 已有两本补充书对应章节图片，但完整OCR曾超时

主教材第2章、第3章结构：
- 第2章：机械零件强度与刚度设计
  - 2.1 机械零件设计概述
  - 2.2 载荷和应力分类
  - 2.3 变应力下机械零件的强度设计
  - 2.4 机械零件的表面强度设计
  - 2.5 机械零件的刚度设计
- 第3章：摩擦、磨损和润滑
  - 3.1 摩擦
  - 3.2 磨损
  - 3.3 润滑

已创建但需修复的脚本：
- `/root/pdf-store/generate_ch2_ch3_foundation_pdf.py`
- 当前错误：ReportLab 不支持直接注册 `/usr/share/fonts/opentype/noto/NotoSerifCJK-Regular.ttc`，报 `postscript outlines are not supported`
- 续做建议：改用 ReportLab CID 字体 `STSong-Light`，或安装/使用可用 TTF 中文字体；然后重新运行生成：
  `/root/pdfenv/bin/python /root/pdf-store/generate_ch2_ch3_foundation_pdf.py`

预期输出文件：
- `机械设计第2章第3章零基础融合讲义.pdf`
- `机械设计第2章第3章零基础融合讲义_源稿.txt`

用户要求：
- 不要再反复确认；实时备份 push
- 注意上下文快满时提前写进度并 push
- 主参考必须是 `mechanical_design_textbook.pdf`
- 不是只按大纲；是先按主教材第2、3章章节名提取，再匹配另外两本教材对应章节内容
