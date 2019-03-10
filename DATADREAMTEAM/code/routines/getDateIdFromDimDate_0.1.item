package routines;

import java.io.Console;
import java.util.Date;
import java.util.HashMap;
import java.util.List;

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
    	/*
    	if(dim_dates != null){
    		//System.out.println("hurray");
    		System.out.println("DIM DATE 160000 : "  + ((HashMap<Integer, Date>) dim_dates).get(160000));
    	} else {
    		System.out.println("fuck de dufkc");
    	} */
    	
    	//  System.out.println("Date Id : "  + DateId);
    	Date date1 = TalendDate.parseDate("yyyy-MM-dd HH:mm:ss", TalendDate.formatDate("yyyy-MM-dd HH:mm:ss", dateEntrante));
        Date date2 = TalendDate.parseDate("yyyy-MM-dd HH:mm:ss", TalendDate.formatDate("yyyy-MM-dd HH:mm:ss", dateSortante));
        
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
            //System.out.println("ok 1 : " + TalendDate.formatDate("HH:mm",date1Heure) );
            //System.out.println("ok 2 : " + TalendDate.formatDate("HH:mm",date2Heure) );

        }
        return DateId;
    }
}
