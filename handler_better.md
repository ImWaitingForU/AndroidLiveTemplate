### 防止内存泄漏handler代码模板


##abbreviation : 
handler_better

##template text:

        private MyHandler mHandler = new MyHandler(this);
        private static class MyHandler extends Handler {
          private WeakReference<Context> reference;
          
          public MyHandler(Context context) {
              reference = new WeakReference<>(context);
          }
          
          @Override
          public void handleMessage(Message msg) {
              MainActivity activity = (MainActivity) reference.get();
              if(activity != null){
                  //todo something
                  $TODO$
              }
          }
       }
 
 
