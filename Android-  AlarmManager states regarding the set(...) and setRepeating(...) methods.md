#Android:  AlarmManager states regarding the set(...) and setRepeating(...) methods

As the API page of AlarmManager states regarding the set(...) and setRepeating(...) methods:

"If the stated trigger time is in the past, the alarm will be triggered immediately, with an alarm count depending on how far in the past the trigger time is relative to the repeat interval."
So, if for example you are on Wednesday, then the AlarmManager will fire the events of: Sunday, Monday, Tuesday and (possibly) Wednesday. It will actually fire only one for all of them.

Here is how I avoid this. Not sure it is the best way, but it works smoothly.

Let's say that you store the day of the week, the hour and the minute of the day in which you want to fire your AlarmManager in the following variables:

final int myAlarmDayOfTheWeek = ...;
final int myAlarmHour = ...;
final int myAlarmMinute = ...;
Of course, here I'm assuming you store the day of the week with the same convention of the Calendar class, i.e.:

Sunday = Calendar.SUNDAY = 1

Monday = Calendar.MONDAY = 2

... ... ...

Saturday = Calendar.SATURDAY = 7