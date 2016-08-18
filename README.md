# webuploader, 最短小精悍的文件上传实现
html5 uploader
#使用方法
极其简单
<pre><code>
1、直接定义事件 onclick="webuploader(this,{})"
2、jquery插件方式：$('selector').webuploader({url:''});
option定义
{
  url: 'upload.ashx?method=upload',
  acceptFiles: 'image/jpeg,image/png,image/jpg',//定义可上传的文件类型
  filesize: 2,//单位M
  success: function (response) {
      var res = response.split(',');
      var self = $(this);
      if (res[0] == "1") {
          var filename = res[1];
          var html = "&lt;img src='" + filename + "' /&gt;";
          $('#photoList').append(html);
      }
      else {
          jAlert("上传失败,原因：" + res[1]);
      }
  }
}
</code></prev>
