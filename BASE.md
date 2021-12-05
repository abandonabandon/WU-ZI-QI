# WU-ZI-QI
import java.util.Scanner;

public class base {

    public static void main(String[] args){
        int[][] x = new int[15][15];
        Scanner sc = new Scanner(System.in);
        do{
            int a = sc.nextInt();
            int b = sc.nextInt();
            int c = sc.nextInt();
            x[a][b] = c;
            for(int i =0;i<15;i++){
                for(int j = 0;j<15;j++){
                    System.out.print(x[i][j]+" ");
                }
                System.out.println();
            }
            if(judgeSuccess(a,b,c,x)){
                System.out.println(c+" win");
                break;
            }
        }while (true);
    }

    public static boolean judgeSuccess(int x, int y, int z,int[][] a){
        int num=1;
        int x1,y1;
        //右
        x1= x;
        y1= y;
        for(int i=1;i<5;i++){
            x1+=1;
            if(x1>14){
                break;
            }
            if(a[x1][y1]== z){
                num++;
            }else{
                break;
            }
        }
        //左
        x1= x;
        for(int i=1;i<5;i++){
            x1-=1;
            if(x1<0){
                break;
            }
            if(a[x1][y1]== z){
                num++;
            }else{
                break;
            }
        }
        if(num==5){
            return true;
        }
        //上
        x1= x;
        y1= y;
        num=1;
        for(int i=1;i<5;i++){
            y1-=1;
            if(y1<0){
                break;
            }
            if(a[x1][y1]== z){
                num++;
            }else{
                break;
            }
        }
        //下
        y1= y;
        for(int i=1;i<5;i++){
            y1+=1;
            if(y1>14){
                break;
            }
            if(a[x1][y1]== z){
                num++;
            }else{
                break;
            }
        }
        if(num==5){
            return true;
        }
        //左上
        x1= x;
        y1= y;
        num=1;
        for(int i=1;i<5;i++){
            x1-=1;
            y1-=1;
            if(y1<0||x1<0){
                break;
            }
            if(a[x1][y1]== z){
                num++;
            }else{
                break;
            }
        }
        //右下
        x1= x;
        y1= y;
        for(int i=1;i<5;i++){
            x1+=1;
            y1+=1;
            if(y1>14||x1>14){
                break;
            }
            if(a[x1][y1]== z){
                num++;
            }else{
                break;
            }
        }
        if(num==5){
            return true;
        }
        //右上
        x1= x;
        y1= y;
        num=1;
        for(int i=1;i<5;i++){
            x1+=1;
            y1-=1;
            if(y1<0||x1>14){
                break;
            }
            if(a[x1][y1]== z){
                num++;
            }else{
                break;
            }
        }
        //左下
        x1= x;
        y1= y;
        for(int i=1;i<5;i++){
            x1-=1;
            y1+=1;
            if(y1>14||x1<0){
                break;
            }
            if(a[x1][y1]== z){
                num++;
            }else{
                break;
            }
        }
        return num == 5;
    }
}
