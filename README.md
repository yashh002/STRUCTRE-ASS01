#include<stdio.h>
#include<string.h>
struct bookinfo{
    char title[20];
    char author[20];
    float price;
    };
    void Insertion(struct bookinfo b[],int d);
    void deletion(struct bookinfo b[],int d);
    void modify(struct bookinfo b[]);
int main()
{
   struct bookinfo b[20];
   int i;
   int d;
   printf("Enter no of books:");
   scanf("%d",&d);
   printf("Enter details of %d books",d);
   for(i=0;i<d;i++) //accepting the info
   {
  
     printf("Enter Title:");
     scanf("%s",b[i].title);
      printf("Enter author:");
     scanf("%s",b[i].author);
     printf("Enter price:");
     scanf("%f",&b[i].price);
     }
     printf("Book details are:\n");
     for(i=0;i<d;i++)  //display the info
     {
     
       printf("%d)\n",i+1);
       printf("Title:%s\n",b[i].title);
       printf("Author:%s\n",b[i].author);
       printf("Price:%.1f\n",b[i].price);
       }
       int ch;
       do{
       printf("MENU\n");
       printf("1.Insertion\n2.Deletion\n3.Modification\n");
       printf("Enter your choice:");
       scanf("%d",&ch);
       switch(ch){
       case 1:Insertion(b,d);
              break;
       case 2:deletion(b,d);
              break;
       case 3:modify(b);
              break;
       default:printf("Exiting program");
       }
       }while(ch!=3);
       return 0;
       }
       void Insertion(struct bookinfo b[],int d){
       int n;
       int i;
       printf("At which position you want to add:");
       scanf("%d",&n);
       for(i=d;i>=n;i--)
       {
         strcpy(b[i+1].title,b[i].title);
         strcpy(b[i+1].author,b[i].author);
         b[i+1].price=b[i].price;
         }
         printf("Enter Your Data:\n");
         printf("Enter Title:");
         scanf("%s",b[n].title);
         printf("Enter author:");
         scanf("%s",b[n].author);
         printf("Enter price:");
         scanf("%f",&b[n].price);
         d++;
       for(i=0;i<d;i++)  //display the info
     {
       printf("%d)\n",i);
       printf("Title:%s\n",b[i].title);
       printf("Author:%s\n",b[i].author);
       printf("Price:%.1f\n",b[i].price);
       }
       }
       void deletion(struct bookinfo b[],int d){
       int c;
       printf("Enter position:");
       scanf("%d",&c);
       int i;
       if(c<0||c>=d){
       printf("Invalid position!");
       }
       else{
       for(i=c;i<(d-1);i++){
       b[i]=b[i+1];
       }
       }
       d--;
       printf("updated record after deletion:\n");
       for(i=0;i<d;i++)  //display the info
     {
       printf("%d)\n",i);
       printf("Title:%s\n",b[i].title);
       printf("Author:%s\n",b[i].author);
       printf("Price:%.1f\n",b[i].price);
       }
       }
       void modify(struct bookinfo b[]){
       int p;
       printf("Enter position to modify:");
       scanf("%d",&p);
       printf("Enter details of book:\n");
       printf("Enter Title:");
         scanf("%s",b[p].title);
         printf("Enter author:");
         scanf("%s",b[p].author);
         printf("Enter price:");
         scanf("%f",&b[p].price);
         printf("Modified details:\n");
       printf("%d)\n",p);
       printf("Title:%s\n",b[p].title);
       printf("Author:%s\n",b[p].author);
       printf("Price:%.1f\n",b[p].price);
       }
       
