## 1：定义

````java

Handler handler = new Handler() {
		@Override
		public void handleMessage(Message msg) {
			 switch(msg.what) {  
	            case 1:  
	            	progress.setProgress(status); 
	                break;   
	            }  	
		}

	};
//meg.obj 可以获得参数

````

## 2:使用

````java
new Thread() {
	public void run() {
		handler.sendEmptyMessage(1);
		//带参数的传值
		//handler.obtainMessage(1,object).sendToTarget();
	}
}.start();

````