# Android-Alarm

AlarmManager 

onReceive(); //execute events 

Context.getSystemService; //get service


//To implement an alarm, you first need to create a class that inherits from BroadcastReceive, 
//implement the onReceive method to receive the Alarm service,
//and then call the Alarm component by establishing an Intent and PendingIntent connection.

ex:
Intent intent = new Intent(Activity01.this, AlarmReceiver.class);
              PendingIntent pendingIntent=PendingIntent.getBroadcast(Activity01.this,0, intent, 0);
              AlarmManager am;							/* get an instance of the alarm management */
              am = (AlarmManager)getSystemService(ALARM_SERVICE);	 			 /* set alarm */
              am.set(AlarmManager.RTC_WAKEUP, calendar.getTimeInMillis(), pendingIntent);		/* set periodic alarm */
              am.setRepeating(AlarmManager.RTC_WAKEUP, System.currentTimeMillis() + (10*1000), (24*60*60*1000), pendingIntent); 
              String tmpS="set the alarm time to "+format(hourOfDay)+":"+format(minute);
              mTextView.setText(tmpS);
