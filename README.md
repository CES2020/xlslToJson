### 文件说明

+ 运行index.html，然后从本地选择要打开的excel文件，可以将excel数据转换为json格式

+ 输出的json数据可以通过控制面板查看

+ 如果一个excel中有多张表，将下边代码的break注释掉即可

```js
// 遍历每张表读取
for (var sheet in workbook.Sheets) {
    if (workbook.Sheets.hasOwnProperty(sheet)) {
        fromTo = workbook.Sheets[sheet]['!ref'];
        persons = persons.concat(XLSX.utils.sheet_to_json(workbook.Sheets[sheet]));
        break; // 只取第一张表，取多张表则注释该行
    }
}
```