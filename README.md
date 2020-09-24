# Bonus-Task

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.ArrayList;
import java.util.Calendar;
import java.util.Date;
import java.util.GregorianCalendar;
import java.util.List;

public class DateFormatExample {
    public static void main(String[] args) {
        // TODO Auto-generated method stub
        SimpleDateFormat myFormat = new SimpleDateFormat("yyyy");
        SimpleDateFormat formatter = new SimpleDateFormat("yyyy");  
        String date1 = "2010";
        String date2 = "2015";
        try {
            Date d1 = myFormat.parse(date1);
            Date d2 = myFormat.parse(date2);
            List<Date> allDates = new ArrayList<Date>();
            List<String> allDatesString = new ArrayList<String>();
            while( d1.before(d2) ){
                d1 = addDays(d1, 1);  
                allDates.add(d1);
                allDatesString.add(formatter.format(d1));
            }
            System.out.println(allDates);
            System.out.println(allDatesString);
        } catch (ParseException e) {
        e.printStackTrace();
        }
    }
    private static Date addDays(Date d1, int i) {
        GregorianCalendar cal = new GregorianCalendar();
        cal.setTime(d1);
        cal.add(Calendar.DATE, 1);
        return cal.getTime();
    }

}
