#include<stdio.h>
#include<stdlib.h>
#include<pthread.h>


int arr[10], i;
int n;


float average=0.0;
float sum=0.0;
int minimum;
int maximum;

//average
void *avg()
{
        for(i=1;i<=n;i++)
                sum=sum+arr[i];
        average=sum/n;
        
}

//minimum value
void *min()
{
        minimum=9999;
        for(int i=1;i<=n;i++)
                if(minimum>arr[i])
                minimum=arr[i];
}

//maximum value
void *max()
{

        maximum=arr[1];
        for(int i=1;i<=n;i++)
                if(maximum<arr[i])
                        maximum=arr[i];
                        
}

int main(int argc, char *argv[])
{
    int count =0;

        for (int i = 1; i < argc; i++)
        {
                arr[i] =  atoi(argv[i]);
                count++;
        }

        n = count;
        printf("%d number entered\n", count);
        for(int i=1; i<=n; i++)
            printf("%d\t",arr[i]);
            
            
        printf("\n--------\n");

    pthread_t thread1;
    pthread_t thread2;
    pthread_t thread3;
    
    //creating threads
        pthread_create(&thread1,NULL,&avg,NULL);
        pthread_join(thread1,NULL);
    
        pthread_create(&thread2,NULL,&min,NULL);
        pthread_join(thread2,NULL);

        pthread_create(&thread3,NULL,&max,NULL);
        pthread_join(thread3,NULL);
        
       
    printf("\nThe sum of given number is %f\n",sum);
    printf("The average value is %f",average);
    printf("\nThe Minimum  value is %d",minimum);
    printf("\nThe Maximum  value is %d",maximum);
        
return 0;

}
