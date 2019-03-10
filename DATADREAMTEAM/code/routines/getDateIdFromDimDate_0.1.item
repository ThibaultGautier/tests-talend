package routines;

import java.util.Date;
import java.util.HashMap;
import java.util.Map.Entry;

/*
 * user specification: the function's comment should contain keys as follows: 1. write about the function's comment.but
 * it must be before the "{talendTypes}" key.
 * 
 * 2. {talendTypes} 's value must be talend Type, it is required . its value should be one of: String, char | Character,
 * long | Long, int | Integer, boolean | Boolean, byte | Byte, Date, double | Double, float | Float, Object, short |
 * Short
 * 
 * 3. {Category} define a category for the Function. it is required. its value is user-defined .
 * 
 * 4. {param} 's format is: {param} <type>[(<default value or closed list values>)] <name>[ : <comment>]
 * 
 * <type> 's value should be one of: string, int, list, double, object, boolean, long, char, date. <name>'s value is the
 * Function's parameter name. the {param} is optional. so if you the Function without the parameters. the {param} don't
 * added. you can have many parameters for the Function.
 * 
 * 5. {example} gives a example for the Function. it is optional.
 */
public class getDateIdFromDimDate {

    /**
     * getClosestDateIdFromDimDate: Envoie le bon id de la dimension date lors du mapping.
     * 
     * 
     * {talendTypes} int
     * 
     * {Category} User Defined
     * 
     * {param} int("DateId") input: L'id de la date correspondate.
     */

    public static int getClosestDateIdFromDimDate(int DateId, Date dateEntrante, Date dateSortante, Object dim_dates) {
    	
    	
        //for(Date dim_date : ((HashMap<Integer, Date>) dim_dates).values()){
    	for (Entry<Integer, Date> e : ((HashMap<Integer, Date>) dim_dates).entrySet()) {
		    Integer key    = e.getKey();
		    Date dim_date  = e.getValue();
	    	//  System.out.println("Date Id : "  + DateId);
	    	Date date1 = TalendDate.parseDate("yyyy-MM-dd HH:mm:ss", TalendDate.formatDate("yyyy-MM-dd HH:mm:ss", dateEntrante));
	        Date date2 = TalendDate.parseDate("yyyy-MM-dd HH:mm:ss", TalendDate.formatDate("yyyy-MM-dd HH:mm:ss", dim_date));
	        
	        String date1Annee = TalendDate.formatDate("yyyy", TalendDate.parseDate("yyyy", TalendDate.formatDate("yyyy-MM-dd HH:mm:ss", date1)));
	        String date2Annee = TalendDate.formatDate("yyyy", TalendDate.parseDate("yyyy", TalendDate.formatDate("yyyy-MM-dd HH:mm:ss", date2)));
	        
	        String date1Mois = TalendDate.formatDate("MM", TalendDate.parseDate("MM", TalendDate.formatDate("MM", date1)));
	        String date2Mois = TalendDate.formatDate("MM", TalendDate.parseDate("MM", TalendDate.formatDate("MM", date2)));
	        
	        String date1Jour = TalendDate.formatDate("dd", TalendDate.parseDate("dd", TalendDate.formatDate("dd", date1)));
	        String date2Jour = TalendDate.formatDate("dd", TalendDate.parseDate("dd", TalendDate.formatDate("dd", date2)));
	
	
		        if(date1Annee.equals(date2Annee) 
		        		&& date1Mois.equals(date2Mois) 
		        		&& date1Jour.equals(date2Jour))
		        {
		            Date date1Heure = TalendDate.parseDate("HH:mm", TalendDate.formatDate("HH:mm", date1));
		            Date date2Heure = TalendDate.parseDate("HH:mm", TalendDate.formatDate("HH:mm", date2));
		            Date date2HeureInterval = TalendDate.addDate(date2Heure, 30, "mm");
			      /*  System.out.println("ok 1 : " + TalendDate.formatDate("HH:mm",date1Heure) );
			        System.out.println("dim date heure : "  + TalendDate.formatDate("HH:mm", date2Heure));
			        System.out.println("dim date heure interval : "  + TalendDate.formatDate("HH:mm", date2HeureInterval));
			        System.out.println("dim date annee mois jour : " + TalendDate.formatDate("yyyy-MM-dd", dim_date));
			        System.out.println("date entrante annee mois jour : " + TalendDate.formatDate("yyyy-MM-dd", date1));
			        System.out.println("Compare : "  + (date1Heure.compareTo(date2Heure) * (date2Heure).compareTo(date2HeureInterval)));
		        */
		            if((date2Heure.compareTo(date1Heure) * (date1Heure).compareTo(date2HeureInterval))>=0){
		            	/* System.out.println("mkay");
		            	System.out.println("full date 1 : " + TalendDate.formatDate("yyyy-MM-dd HH:mm",date1) );
		            	System.out.println("full date 2 : " + TalendDate.formatDate("yyyy-MM-dd HH:mm",date2) );
		            	System.out.println("ok 1 : " + TalendDate.formatDate("HH:mm",date1Heure) );
				        System.out.println("dim date heure : "  + TalendDate.formatDate("HH:mm", date2Heure));
				        System.out.println("dim date heure interval : "  + TalendDate.formatDate("HH:mm", date2HeureInterval));
				        System.out.println(key); */
		            	return key;
		            } /* else {
		            	System.out.println("oopsies");
		            } */
		        }
        }
        return -1;
    }
}
