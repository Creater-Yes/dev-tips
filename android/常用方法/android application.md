次对象可以做一些全局设置的事情。使用方法：


##	1：继承appliacation

````java

package com.topnews.app;

import java.io.File;

import com.nostra13.universalimageloader.cache.disc.impl.UnlimitedDiscCache;
import com.nostra13.universalimageloader.cache.disc.naming.Md5FileNameGenerator;
import com.nostra13.universalimageloader.core.ImageLoader;
import com.nostra13.universalimageloader.core.ImageLoaderConfiguration;
import com.nostra13.universalimageloader.core.assist.QueueProcessingType;
import com.nostra13.universalimageloader.utils.StorageUtils;
import com.topnews.db.SQLHelper;

import android.app.Application;
import android.content.Context;
import android.util.Log;

public class AppApplication extends Application {
 	
	//整体创建的时候调用这个方法
	@Override
	public void onCreate() {
		// TODO Auto-generated method stub
		super.onCreate();
		 
	}	 	  
 
	//整体摧毁的时候调用这个方法
	@Override
	public void onTerminate() {
		 
		super.onTerminate();
		
	}
	 
}

````


##	2：在manifast中配置

````java
    <application
        android:name=".app.AppApplication" // 配置
        android:allowBackup="true"
        android:icon="@drawable/icon"
        android:label="@string/app_name"
        android:theme="@style/AppTheme" >

````