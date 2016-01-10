````java

NotificationManager notificationManager ;

//user code
//获取系统通知管理
notificationManager = (NotificationManager) getSystemService(NOTIFICATION_SERVICE);
//启动intent
 Context context = TestActivity.this;
 Intent intent = new Intent(context, TestActivity.class);  
 PendingIntent pi = PendingIntent.getActivity(this, 0, intent, 0);  	
 
 Notification notify= null;
 if(android.os.Build.VERSION.SDK_INT > 16){
	 notify = new Notification.Builder(context)
			 //设置提示字体
			 .setTicker("new msg form：" + context.getResources().getString(R.string.app_name))
			 .setContentTitle("Title")
			 .setContentText("Text")
			 //默认声音和灯光
			 .setDefaults(Notification.DEFAULT_SOUND | Notification.DEFAULT_LIGHTS)
			 .setSmallIcon(R.drawable.ic_launcher)
			 .build();
 }
 else//16版本以下的方法
 {
	 notify = new Notification.Builder(context)
	 .setContentTitle("Title").setContentText("Text")
	 .setSmallIcon(R.drawable.ic_launcher).getNotification();
 }
 notificationManager.notify(1,notify);

````