#### excal 文件下载

```
// 导出excel
exportExcel(data, title) {
    if (!data) return;
    let url = window.URL.createObjectURL(new Blob([data]));
    let link = document.createElement('a')
    link.style.display = 'none'
    link.href = url
    link.setAttribute('download', title + this.TimeCycle(new Date().getTime()) + '.xlsx')
    document.body.appendChild(link)
    link.click()
    document.body.removeChild(link)
},
```

```
exportList() {
      if (!this.dataList.length) {
        this.$message.warning("未查询出数据，无法导出");
        return false;
      }
      let dataLink = this.GlobalVal.httpLink.exportTurnClassRefund + "?";
      for (let i in this.objData) {
        this.objData[i] &&
          i !== "page" &&
          i !== "limit" &&
          (dataLink += i + "=" + this.objData[i] + "&");
      }
      window.open(dataLink);
```

