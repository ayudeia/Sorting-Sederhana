import java.util.Scanner;
public class Sortin {
    public static void main(String[] args){
        Scanner Data = new Scanner(System.in);
        int choose, age, pilih;
        String name, address, ageStr;

        int index = 0;
        String arr[][] = new String[100][3];
        String temp[] = new String[3];

        do {
            System.out.println("\n        Patient's Data          ");
            System.out.println("        ++++++++++++++          ");
            System.out.println(" ");
            System.out.println("1. Input New Data");
            System.out.println("2. View Patient's Data");
            System.out.println("3. Exit");

            System.out.println("");
            System.out.print("Choose: ");
            choose = Data.nextInt();
            Data.nextLine();

            switch(choose){
                case 1:
                
                do{ 
                    System.out.print("Input Name [3...20]: ");
                    name = Data.nextLine();
                }while (name.length() < 3 || name.length() > 20);
                

                while (true){
                    System.out.print("Input Age [10...100]: ");
                    try {
                        age = Data.nextInt();
                        Data.nextLine();
                        ageStr = String.valueOf(age);
                        break;
                    } catch (Exception e) {
                        Data.nextLine();
                    }
                }
                
                    
                do{
                    System.out.print("Input Address [5...30]: ");
                    address = Data.nextLine();
                }while (address.length() < 5 || address.length() > 30);
                
                arr[index][0] = name;
                arr[index][1] = ageStr;
                arr[index][2] = address;
                index++;
                
                System.out.println(" ");
                System.out.println("Data Has Been Successfully Inserted!");
                break;


                case 2:
                System.out.println("No. | Name                | Age   | Address");
                System.out.println("=====================================================");
                for(int x=0; x<index; x++) {
                    System.out.println(x+1 + "   | " +arr[x][0]+ "                | "+arr[x][1]+"    | "+arr[x][2]);
                }

                System.out.println("");
                System.out.println("1. Sort Data By Name Ascending");
                System.out.println("2. Sort Data By Name Descending");
                System.out.println("3. Sort Data By Age Ascending");
                System.out.println("4. Sort Data By Age Descending");
                System.out.println("5. Back");
                System.out.print("Choose: ");
                pilih = Data.nextInt();

                
                switch (pilih){
                    case 1:
                    for (int x = 0; x < index-1; x++){
                        for (int y = 0; y < index-x-1; y++){
                            if (arr[y][0].compareTo(arr[y+1][0]) > 0){
                                temp = arr[y];
                                arr[y] = arr[y+1];
                                arr[y+1] = temp;
                            }
                        }
                    }
                    System.out.println("Data Sorted");
                    break;

                    case 2:
                    for (int x = 0; x < index-1; x++){
                        for (int y = 0; y < index-x-1; y++){
                            if (arr[y][0].compareTo(arr[y+1][0]) < 0){
                                temp = arr[y];
                                arr[y] = arr[y+1];
                                arr[y+1] = temp;
                            }
                        }
                    }
                    System.out.println("Data Sorted");
                    break;

                    case 3:
                    for (int x = 0; x < index-1; x++){
                        for (int y = 0; y < index-x-1; y++){
                                if (arr[y][1].compareTo(arr[y+1][1]) > 0){
                                    temp = arr[y];
                                    arr[y] = arr[y+1];
                                    arr[y+1] = temp;
                                }
                            
                            
                        }
                    }
                    System.out.println("Data Sorted");
                    break;

                    case 4:
                    for (int x = 0; x < index-1; x++){
                        for (int y = 0; y < index-x-1; y++){
                                if (arr[y][1].compareTo(arr[y+1][1]) < 0){
                                    temp = arr[y];
                                    arr[y] = arr[y+1];
                                    arr[y+1] = temp;
                                }
                            
                            
                        }
                    }
                    System.out.println("Data Sorted");
                    break;
                    
                    case 5:
                    break;
                }
                case 3:
                break;
            }

        }while(choose!=3);
    }
}
