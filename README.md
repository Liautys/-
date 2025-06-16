------------------------------------------------------------------------------作者：VerdGard
-----------------------------------------------------------------------------

导入"android.graphics.PorterDuffColorFilter"
导入"android.图形.波特达夫"

函数MD提示(str，color，color2，ele，rad)
如果时间，则toasttime=Toast.LENGTH_SHORT否则toasttime=Toast.LENGTH_SHORT结束
祝酒词={
cardview；
ID="toastb"，
CardElevation=ele；
半径=弧度；
backgroundColor=color；
    {
TextView；
layout_margin="7dp"；
textSize="13sp"；
TextColor=color2，
text=str；
layout_gravity=“中心”；
ID="mess"，
    };
  };
local toast=Toast.makeText(活动，无，toasttime)；
toast.setView(loadlayout(toasts))
toast.show()
end

功能窗口标题(文本)
activity.setTitle(文本)
end

功能载入界面(id)
activity.setContentView(loadlayout(id))
end

功能隐藏标题栏()
activity.ActionBar.hide()
end

功能设置主题(id)
activity.setTheme(id)
end

功能打印(文本)
打印(文本)
end

功能窗口全屏()
活动。GetWindow().setflags(WindowManager.LayoutParams.Flag_FULLSCREEN，WindowManager.LayoutParams.Flag_FULLSCREEN)
end

功能取消全屏()
活动。GetWindow()。clearFlags(WindowManager.LayoutParams.Flag_FULLSCREEN)
end

功能返回桌面()
activity.moveTaskToBack(true)
end

函数提示(文本)
吐司面包。makeText(活动，文本，Toast.Length_SHORT)。显示()
end

功能截取文本(str，str1，str2)
str1=str1:gsub("%p"，函数返回("%"..s)结束)
return str:match(str1.."(. -)"..str2)
end

功能替换文本(str，str1，str2)
str1=str1:gsub("%p"，函数返回("%"..s)结束)
str2=str2:gsub(%%"，%%%")
return str:gsub(str1，str2)
end

功能字符串长度(str)
return utf8.len(str)
end

功能状态栏颜色(颜色)
如果Build.VERSION.SDK_INT>=21，则
活动。GetWindow().AddFlags(WindowManager.LayoutParams.Flag_DRAWS_SYSTEM_BAR_BACKGROUNDS)。setStatusBarColor(颜色)；
  end
end

function 沉浸状态栏()
  if Build.VERSION.SDK_INT >= 19 then
    activity.getWindow().addFlags(WindowManager.LayoutParams.FLAG_TRANSLUCENT_STATUS);
  end
end

function 设置文本(id,text)
  id.Text=text
end

function 跳转页面(name)
  activity.newActivity(name)
end

function 跳转界面(name)
  activity.newActivity(name)
end

function 关闭页面()
  activity.finish()
end

function 关闭界面()
  activity.finish()
end

function 获取文本(id)
  return id.Text
end

function 结束程序()
  activity.finish()
end

function 重构页面()
  activity.recreate()
end

function 重构界面()
  activity.recreate()
end

function 控件圆角(view,InsideColor,radiu)
  import "android.graphics.drawable.GradientDrawable"
  drawable = GradientDrawable()
  drawable.setShape(GradientDrawable.RECTANGLE)
  drawable.setColor(InsideColor)
  drawable.setCornerRadii({radiu,radiu,radiu,radiu,radiu,radiu,radiu,radiu});
  view.setBackgroundDrawable(drawable)
end

function 获取设备标识码()
  import "android.provider.Settings$Secure"
  return Secure.getString(activity.getContentResolver(), Secure.ANDROID_ID)
end

function 获取IMEI()
  import "android.content.Context"
  return activity.getSystemService(Context.TELEPHONY_SERVICE).getDeviceId()
end

function 控件背景渐变动画(view,color1,color2,color3,color4)
  import "android.animation.ObjectAnimator"
  import "android.animation.ArgbEvaluator"
  import "android.animation.ValueAnimator"
  import "android.graphics.Color"
  colorAnim = ObjectAnimator.ofInt(view,"backgroundColor",{color1, color2, color3,color4})
  colorAnim.setDuration(3000)
  colorAnim.setEvaluator(ArgbEvaluator())
  colorAnim.setRepeatCount(ValueAnimator.INFINITE)
  colorAnim.setRepeatMode(ValueAnimator.REVERSE)
  colorAnim.start()
end

function 获取屏幕尺寸(ctx)
  import "android.util.DisplayMetrics"
  dm = DisplayMetrics();
  ctx.getWindowManager().getDefaultDisplay().getMetrics(dm);
  diagonalPixels = Math.sqrt(Math.pow(dm.widthPixels, 2) + Math.pow(dm.heightPixels, 2));
  return diagonalPixels / (160 * dm.density);
end

function 是否安装APP(packageName)
  if pcall(function() activity.getPackageManager().getPackageInfo(packageName,0) end) then
    return true
   else
    return false
  end
end

function 设置中划线(id)
  import "android.graphics.Paint"
  id.getPaint().setFlags(Paint. STRIKE_THRU_TEXT_FLAG)
end

function 设置下划线(id)
  import "android.graphics.Paint"
  id.getPaint().setFlags(Paint. UNDERLINE_TEXT_FLAG)
end

function 设置字体加粗(id)
  import "android.graphics.Paint"
  id.getPaint().setFakeBoldText(true)
end

function 设置斜体(id)
  import "android.graphics.Paint"
  id.getPaint().setTextSkewX(0.2)
end

function 分享内容(text)
  intent=Intent(Intent.ACTION_SEND);
  intent.setType("text/plain");
  intent.putExtra(Intent.EXTRA_SUBJECT, "分享");
  intent.putExtra(Intent.EXTRA_TEXT, text);
  intent.setFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
  activity.startActivity(Intent.createChooser(intent,"分享到:"));
end

function 加QQ群(qq)
  import "android.net.Uri"
  import "android.content.Intent"
  activity.startActivity(Intent(Intent.ACTION_VIEW, Uri.parse("mqqapi://card/show_pslcard?src_type=internal&version=1&uin="..qq.."&card_type=group&source=qrcode")))
end

function 跳转QQ群(qq)
  import "android.net.Uri"
  import "android.content.Intent"
  activity.startActivity(Intent(Intent.ACTION_VIEW, Uri.parse("mqqapi://card/show_pslcard?src_type=internal&version=1&uin="..qq.."&card_type=group&source=qrcode")))
end

function QQ聊天(qq)
  import "android.net.Uri"
  import "android.content.Intent"
  activity.startActivity(Intent(Intent.ACTION_VIEW, Uri.parse("mqqwpa://im/chat?chat_type=wpa&uin="..qq)))
end

function 跳转QQ聊天(qq)
  import "android.net.Uri"
  import "android.content.Intent"
  activity.startActivity(Intent(Intent.ACTION_VIEW, Uri.parse("mqqwpa://im/chat?chat_type=wpa&uin="..qq)))
end

function 发送短信(phone,text)
  require "import"
  import "android.telephony.*"
  SmsManager.getDefault().sendTextMessage(tostring(phone), nil, tostring(text), nil, nil)
end

function 获取剪切板()
  import "android.content.Context"
  return activity.getSystemService(Context.CLIPBOARD_SERVICE).getText()
end

function 写入剪切板(text)
  import "android.content.Context"
  activity.getSystemService(Context.CLIPBOARD_SERVICE).setText(text)
end

function 开启WIFI()
导入“android.content.Context”
  wifi = activity.Context.getSystemService(Context.WIFI_SERVICE)
  wifi.setWifiEnabled(true)
end

function 关闭WIFI()
导入“android.content.Context”
  wifi = activity.Context.getSystemService(Context.WIFI_SERVICE)
  wifi.setWifiEnabled(false)
end

function 断开网络()
导入"android.content.Context"
  wifi = activity.Context.getSystemService(Context.WIFI_SERVICE)
  wifi.disconnect()
end

function 创建文件(file)
  import "java.io.File"
  return File(file).createNewFile()
end

function 创建文件夹(file)
  import "java.io.File"
  return File(file).mkdir()
end

function 创建多级文件夹(file)
  import "java.io.File"
  return File(file).mkdirs()
end

function 移动文件(file,file2)
  import "java.io.File"
  return File(file).renameTo(File(file2))
end

function 写入文件(file,text)
  return io.open(file,"w"):write(text):close()
end

function 设置按钮颜色(id,color)
  id.getBackground().setColorFilter(PorterDuffColorFilter(color,PorterDuff.Mode.SRC_ATOP))
end

function 设置编辑框颜色(id,color)
  id.getBackground().setColorFilter(PorterDuffColorFilter(color,PorterDuff.Mode.SRC_ATOP));
end

function 设置进度条颜色(id,color)
  id.IndeterminateDrawable.setColorFilter(PorterDuffColorFilter(color,PorterDuff.Mode.SRC_ATOP))
end

function 设置控件颜色(id,color)
  id.setBackgroundColor(color)
end

function 获取手机存储路径()
  return Environment.getExternalStorageDirectory().toString()
end

function 获取屏幕宽()
  return activity.getWidth()
end

function 获取屏幕高()
  return activity.getHeight()
end

function 文件是否存在(file)
  return File(file).exists()
end

function 关闭左侧滑(id)
  id.closeDrawer(3)
end

function 打开左侧滑()
  id.openDrawer(3)
end

function 显示控件(id)
  id.setVisibility(0)
end

function 隐藏控件(id)
  id.setVisibility(8)
end

function 播放本地音乐(url)
  import "android.content.Intent"
导入"android.net.Uri"
  intent = Intent(Intent.ACTION_VIEW)
  uri = Uri.parse("file://"..url)
  intent.setDataAndType(uri, "audio/mp3")
  this.startActivity(intent)
end

function 在线播放音乐(url)
  import "android.content.Intent"
导入"android.net.Uri"
  intent = Intent(Intent.ACTION_VIEW)
  uri = Uri.parse(url)
  intent.setDataAndType(uri, "audio/mp3")
  this.startActivity(intent)
end

function 播放本地视频(url)
  import "android.content.Intent"
导入"android.net.Uri"
  intent = Intent(Intent.ACTION_VIEW)
  uri = Uri.parse("file://"..url)
  intent.setDataAndType(uri, "video/mp4")
  activity.startActivity(intent)
end

function 在线播放视频(url)
  import "android.content.Intent"
  import "android.net.Uri"
  intent = Intent(Intent.ACTION_VIEW)
  uri = Uri.parse(url)
  intent.setDataAndType(uri, "video/mp4")
  activity.startActivity(intent)
end

function 打开APP(packageName)
  import "android.content.Intent"
  import "android.content.pm.PackageManager"
  manager = activity.getPackageManager()
  open = manager.getLaunchIntentForPackage(packageName)
  this.startActivity(open)
end

function 卸载APP(file)
导入"android.net.Uri"
  import "android.content.Intent"
  uri = Uri.parse("package:"..file)
  intent = Intent(Intent.ACTION_DELETE,uri)
  activity.startActivity(intent)
end

function 安装APP(file)
  import "android.content.Intent"
导入"android.net.Uri"
  intent = Intent(Intent.ACTION_VIEW)
  intent.setDataAndType(Uri.parse("file://"..file), "application/vnd.android.package-archive")
  intent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK)
  activity.startActivity(intent)
end

功能系统下载文件(url，目录，名称)
导入"android.content.Context"
导入"android.net.Uri"
downloadManager=activity.getSystemService(上下文。下载_服务)；
URL=Uri.parse(url)；
request=DownloadManager.Request(url)；
请求。setAllowedNetworkTypes(DownloadManager。请求。network_MOBILE|DownloadManager。请求。network_WIFI)；
请求。setDestinationInExternalPublicDir(目录，名称)；
请求。setNotificationVisibility(DownloadManager。请求。visibility_VISIBLE_NOTIFY_COMPLETED)；
downloadManager.enqueue(请求)；
end

功能调用系统下载文件(url，目录，名称)
导入"android.content.Context"
导入"android.net.Uri"
downloadManager=activity.getSystemService(上下文。下载_服务)；
URL=Uri.parse(url)；
request=DownloadManager.Request(url)；
请求。setAllowedNetworkTypes(DownloadManager。请求。network_MOBILE|DownloadManager。请求。network_WIFI)；
请求。setDestinationInExternalPublicDir(目录，名称)；
请求。setNotificationVisibility(DownloadManager。请求。visibility_VISIBLE_NOTIFY_COMPLETED)；
downloadManager.enqueue(请求)；
结束

function弹窗1(标题、内容、文本、趣味)
dialog=AlertDialog.Builder(this)
.setTitle(标题)
.setMessage(内容)
.setPositiveButton(文本，{onClick=fun})
.show()
dialog.create()
结束

功能确定弹窗(标题、内容、文本、fun)
dialog=AlertDialog.Builder(this)
.setTitle(标题)
.setMessage(内容)
.setPositiveButton(文本，{onClick=fun})
.show()
dialog.create()
结束

函数波纹(id，color)
导入"android.content.res.ColorStateList"
本地attrsArray={android。R。attr.selectableItemBackgroundBorderless}
本地TypedArray=活动。GetStyledAttributes(attrsArray)
ripple=typedArray.getResourceId(0，0)
Aoos=activity.Resources.getDrawable(ripple)
aoos.setColor(ColorStateList(int[0].class{int{}}，int{color}))
身份标识。setBackground(Aoos.setColor(ColorStateList(int[0].class{int{}}，int{color})))
结束

功能添加波纹效果(id，color)
导入"android.content.res.ColorStateList"
本地attrsArray={android。R。attr.selectableItemBackgroundBorderless}
本地TypedArray=活动。GetStyledAttributes(attrsArray)
ripple=typedArray.getResourceId(0，0)
Aoos=activity.Resources.getDrawable(ripple)
aoos.setColor(ColorStateList(int[0].class{int{}}，int{color}))
身份标识。setBackground(Aoos.setColor(ColorStateList(int[0].class{int{}}，int{color})))
结束

函数随机数(最小值，最大值)
返回数学.随机(最小值，最大值)
end

功能删除控件(id，id2)
return(id).removeView(id2)
end

功能状态栏亮色()
如果Build.VERSION.SDK_INT>=23，则
活动。getDecorView()。setSystemUiVisibility(View.System_UI_FLAG_LIGHT_STATUS_BAR)；
结束
end
