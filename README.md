# Banking-System
#include<stdio.h>
#include<conio.h>  
int list();
void diposite();
void last();
void withdraw();
void transfer();
void checkDetail();
void help();
int TotalAmount=100000,Amount,Amo,Tr,TotalDiposite=0,TotalWith=0,TotalTr=0;
int Acc;
char name[10];
int main()
	{
	printf("********WELCOME********\nEnter your name : ");
	scanf("%[^\n]*c",&name);
	printf("Enter the account number : ");
	scanf("%d",&Acc);
   while(1)
{
switch(list())
 { 
   case 1:
   	      diposite();
   	      TotalDiposite+=Amount;
   	      break;
   case 2:
   	      withdraw();
   	      if(Amo<=TotalAmount)
   	      TotalWith+=Amo;
   	      break;
   case 3:
          transfer();
          if(Tr<=TotalAmount)
          TotalTr+=Tr;
          break;
   case 4:
   	      checkDetail();
   	      break;
   case 5:
   	      last();
   	      getch();
          exit(0);
   case 6:
          help(); 
		  break;      
   default:
       printf("\nInvalid Choice");	
     }  
   getch();
  }
}

int list()
{
	  int ch;
	  printf("\n1: Deposite Amount : ");
	  printf("\n2: Withdraw Amount : ");
	  printf("\n3: Trasfer Amount : ");
	  printf("\n4: Check Detail : ");
	  printf("\n5: Exit :");
	  printf("\n6: Help and Support : ");
	  printf("\nEnter Your Choice : ");
	  scanf("%d",&ch);
	  return(ch);
}
void diposite()
 { 
    printf("\nEnter The Amount You Want To diposite : ");
    scanf("%d",&Amount);
    printf("Deposite Amount %d Successful",Amount);
    TotalAmount+=Amount;
 }
 void withdraw()
 {
 	printf("\nEnter The Amount You Want to Withdraw : ");
 	scanf("%d",&Amo);
 	if(Amo<=TotalAmount)
 	printf("Withdraw Amount %d Successful",Amo);
 	 TotalAmount-=Amo;
 	 else
 	printf("\nSorry Withdraw Amount Is More Than Your Avaliable Balance, Withdraw Not Possible");
 }
 void transfer()
 {
 	printf("\nEnter The Amount You Want To Transfer : ");
 	scanf("%d",&Tr);
 	 if(Tr<=TotalAmount)
 	 printf("Transfer Amount %d Successful",Tr);
 	TotalAmount-=Tr;
 	 else
 	printf("\nTransfer Amount is More Than Availiable Balance,Transfer Not Possible");
 }
 void checkDetail()
 {
 	printf("\nTotal Amount = %d",TotalAmount);
 	printf("\nTotal Diposited Amount = %d",TotalDiposite);
 	printf("\nTotal Withdraw Amount = %d",TotalWith);
 	printf("\nTotal Transfered Amount = %d",TotalTr);
 }
 void last()
 {	printf("\nYour Name =%s",name);
    printf("\nAccount Number=%d",Acc);
	printf("\nTotal Amount = %d",TotalAmount);
 	printf("\nTotal Diposited Amount = %d",TotalDiposite);
 	printf("\nTotal Withdraw Amount = %d",TotalWith);
 	printf("\nTotal Transfered Amount = %d",TotalTr);
 	printf("\n*-*-*-*-*-THANK YOU-*-*-*-*-*\n");
 	printf("*-*-*-*-*-HAVE A NICE DAY-*-*-*-*-*");

 }
 void help()
 {
 	printf("****Thank You For Contacting Us****\n\nPlease dial to our coustomer care service at '1800 7782 7747'\nEmail : bankofindia@gmail.com\nPress *ENTER* For MAIN MENU");
 }
