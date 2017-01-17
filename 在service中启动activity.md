  





在一个service中启动一个其他的应用中的activity



	Intent intent = new Intent(this,SecondActivity.class);
    intent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
    startActivity(intent);

运行后activity就成功启动了。

总结：如果一个外部的Activity Context调用startActivity方法，那么，Intent对象必须包含 FLAG_ACTIVITY_NEW_TASK标志，这是因为，待创建的Activity并没有从一个已经存在的Activity启动（任务栈中并没有此Activity），它并没有已经存在的任务，因此它需要被放置在自己独立的任务中（也就是在任务栈中新建一个任务）。