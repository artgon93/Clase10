# Clase10


    public int[] iniciarVecRdm(int[] vector){
        int vec[] = vector;
        for (int i=0; i<=vec.length-1; i++){       
            vec[i]=(int) (Math.random()*30+1);            
        }
        return vec;              
    }
    
    public int[] seleccion(int[] vector){
        int vec[] = vector;
        int vec2[];
        vec2 = new int[5];
        for (int i=0; i<=vec.length-1; i){  
            for(int j=0; i<=vec.length-1;j++){
                if(vec[i]<vec[i+1]){
                    vec2[j]=vec [i];
                    i++;
                }
                  
            }
        }
        return vec2;
    } 



/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package practicaexamenii;

/**
 *
 * @author Estudiantes
 */
public class PracticaExamenII {

    /**
     * @param args the command line arguments
     */
    
    
    
    public static void main(String[] args) {
        // TODO code application logic here
        int mat[][] = new int[4][4];
        Funciones vPractica  = new Funciones();

        vPractica.iniciarMatRdm(mat);
        System.out.println(vPractica.mostrarMat(mat));
        
        vPractica.adyacentes(mat, 2, 2, 1);
    }
    
}



package practicaexamenii;

/**
 *
 * @author Estudiantes
 */
public class Funciones {
    public int[][] iniciarMatRdm(int[][] matriz){
        int mat[][] = matriz;
        for (int i=0; i<=mat.length-1; i++){  
          for (int j=0; j<=mat.length-1; j++){
              mat[i][j]=(int) (Math.random()*2+1);
          }            
        }
        return mat;              
    }
    
    public String mostrarMat(int[][] mat){
        String str ="";
        for (int i=0; i<=mat.length-1; i++){ 
            for(int j=0; j<=mat.length-1; j++){
                if(j != mat.length-1){
                    str += mat[i][j] + ", ";  
                }else{
                    str += mat[i][j] + System.lineSeparator();
                }             
            }
        }
        return str;              
    }
    
    public void adyacentes(int[][] mat, int fila, int colum, int num){
        //String str = "";
        for (int i=0; i<=mat.length-1; i++){ 
            for(int j=0; j<=mat.length-1; j++){
                if (mat [i+1][j] == num){
                    mat [i+1][j] = -1 ;
                }else if (mat [i+1][j] == mat[i][j]){
                    mat [i+1][j] = -1 ;
                    
                if (mat [i-1][j] == num){
                    mat [i-1][j] = -1 ;
                }else if (mat [i-1][j] == mat[i][j]){
                    mat [i-1][j] = -1 ;
                }
                
                if (mat [i][j+1] == num){
                    mat [i][j+1] = -1 ;
                }else if (mat [i][j+1] == mat[i][j]){
                    mat [i][j+1] = -1 ;
                }

                if (mat [i][j-1] == num){
                    mat [i][j-1] = -1 ;
                }
                else if (mat [j][j-1] == mat[i][j]){
                    mat [i][j-1] = -1 ;    

                }           
            }
        }
       // return str;
    }
}
}
