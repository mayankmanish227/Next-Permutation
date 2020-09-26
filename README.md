# Next-Permutation


import java.util.*;

public class HelloWorld
{
     public static void main(String []args)
     {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        String s=String.valueOf(n);
        int[] arr=new int[s.length()];
        int i=s.length()-1;
        while(n>0)
        {
            arr[i]=n%10;
            n=n/10;
            i--;
           // System.out.println(i);
        }
        int q=s.length()-1;
        int top=arr[q];
        int next=arr[q-1];
           int count=0;
        while(top<next)
        {
            if((q-1)==-1)
            {
                System.out.println("Not Possible");
                count++;
                break;
            }
            top=arr[q];
            next=arr[q-1];
            if(next>top)
            {
               // System.out.println(q);
                q--;
            }
            else if(top>next)
            {
                top=q;
                next=q-1;
                //System.out.println(top+" "+next);
            }
        }
        if(count==0)
        {
            int min=arr[top];
            int ind=0;
         
            for(int i1=top;i1<arr.length;i1++)
            {
                if(min>arr[i1])
                {
                    min=arr[i1];
                    ind=i1;
            
                }
            }
            
            int temp=arr[next];
            arr[next]=arr[ind];
            arr[ind]=temp;
            
            List<Integer> li=new ArrayList<>();
            for(int g=top;g<arr.length;g++)
            {
                li.add(arr[g]);
            }
            Collections.sort(li);
            int b=0;
            for(int g=top;g<arr.length;g++)
            {
                arr[g]=li.get(b);
                b++;
            }
            for(int r=0;r<arr.length;r++)
            {
                System.out.print(arr[r]);
            }
        }
        
     }
}
