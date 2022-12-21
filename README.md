# CHAMBRE
1. Parcourir un ArrayList
        List<Integer> listSorted =  arrayList.stream()
                .map(age -> (int)age*2)
                .filter(age -> (int)age > 24)
                .collect(Collectors.toList());
				
2. Gérer différents types d'exceptions
        try{

        }catch(Exception  e){
        } finally {
        }

3. Utiliser les règles de visibilité
Visible to the package, the default. No modifiers are needed.
Visible to the class only (private).
Visible to the world (public).
Visible to the package and all subclasses (protected).


4. Vérifier si une chaîne de caractères est un palindrome

          Static boolean palFunction(String str){
          String upStr = str.toUpperCase();
          int i = 0;
          int j = upStr.length();
          
          while(i<j){
          if(upStr.charAt(i) !=  upStr.charAt(j) )
          return true;
          
          i++;
          j--;
          }
          return true;
          
          }
5. Copier un tableau  



         static int[] copyArray(int[] array){
	     
             int[] cArray = new int[array.length];
			 
			 //System.arraycopy(array,0,cArray,0,array.length);
	     
             for(int i =0 ; i<array.length ; i++){
                 cArray[i] = array[i];
             }
             return cArray;
	     
         }
6. Copier un fichier vers un autre

        try(InputStream is = new FileInputStream(src);
            OutputStream os = new FileOutputStream(dest){
        	
        	byte[] buffer = new byte[2048];
        	int len;
        	
        	while((len = is.read(buffer)) != -1){
        	os.write(buffer,0,len);
        	}
        }
7. Créer un HashMap et contraindre son type de clés et de valeurs

        HashMap<Integer,String> map=new HashMap<Integer,String>();
        map.put(1,"Mango"); 
        map.put(2,"Apple");
        map.put(3,"Banana");
        map.put(4,"Grapes");
        for(Map.Entry<Integer, String> m : map.entrySet()){
            System.out.println(m.getKey()+" "+m.getValue());
        }
		
8. Créer une classe Singleton

   //create an object of SingleObject
   private static SingleObject instance = new SingleObject();

   //make the constructor private so that this class cannot be
   //instantiated
   private SingleObject(){}

   //Get the only object available
   public static SingleObject getInstance(){
      return instance;
   }
   
   
9. Créer une classe qui étend la classe java.io.PrintStream

public class WebPrintStream extends PrintStream {


    public WebPrintStream(OutputStream out, boolean autoFlush) {
        super(out, autoFlush);
    }

    public void printbr(Object obj) {

        this.print(String.valueOf(obj) + " [it] <br/> [/it].");

    }

    public static void main(String[] args) {
        WebPrintStream webPrintStream = new WebPrintStream(System.out, true);
        webPrintStream.print("bah");
    }
}

10. Ecrire un algorithme dichotomique

 public static void binarySearch(int tab[], int f, int l, int val){
    int mid = (f + l)/2;
    while(f <= l){
      if (tab[mid] < val){
        f = mid + 1;   
      }else if(tab[mid] == val){
        System.out.println("L'élément se trouve à l'index: " + mid);
        break;
      }else{
         l = mid - 1;
      }
      mid = (f + l)/2;
   }
    if (f > l){
      System.out.println("L'élément n'existe pas!");
    }
   }




