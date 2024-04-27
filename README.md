# Hanoi

# //////////////////
# //汉诺塔Java实现
# //////////////////

package hello;
 
import java.util.Scanner; 
 
 
public class Hello {
 
	//汉诺塔算法过程
    //移动塔盘描述
	public static void move(int n,char from,char to){
    	System.out.println("Put "+n+" from "+from+" to "+to);//移动塔盘n从from（初始）到to（目的）
    }
	//移动过程
    public static void hanoi(int n,char from,char dependence,char to){
    	if(n==1){
    		move(n,from,to);//当n==1时，直接将塔盘1从from移动到to
    	}
    	else{
    		hanoi(n-1,from,to,dependence);//当n!=1时，先将n-1移动到借助塔（借助目的塔）
    		move(n,from,to);              //再将n移动到目的塔
    		hanoi(n-1,dependence,from,to);//最后将借助塔上的移动到目的塔（借助初始塔）
    	}
    }
    //主函数
    public static void main(String[] args){
    	char from = 'A',dependence = 'B',to = 'C';
    	while(true){//while只能跟bool型，如true，false，1==1等
    		Scanner in = new Scanner(System.in);
        	int n;
        	System.out.println("input a number from keyboard,please");
        	n = in.nextInt();
        	hanoi(n,from,dependence,to);
    	}
    	
    }
}
