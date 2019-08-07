# java_code-max_char_distinct_char

import java.util.*;
import java.io.*;
public class Non_repeat_char
{
static int n_char=256;
public static int max_size_sub(String s)
{
int n=s.length();
int in_length=1;
int max_length=1;
int p_index;
int trav[]=new int[n_char];
for(int i=0;i<n_char;i++)
{
	trav[i]=-1;
}
trav[s.charAt(0)]=0;
for(int i=1;i<n;i++)
{
	p_index=trav[s.charAt(i)];
	if(p_index==-1||i-in_length > p_index)
		in_length++;
	else{
		if(in_length>max_length)
		in_length=max_length;
		in_length=i-p_index;
	}
	trav[s.charAt(i)]=i;
}
	if(in_length>max_length)
		max_length=in_length;
	return max_length;
	}
	public static void main(String[] args)
	{
		String s;
		Scanner as=new Scanner(System.in);
		s=as.nextLine();
		int l = max_size_sub(s);
		System.out.println(l);
	 }
}
		
		
		
	
