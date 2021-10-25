
#include <stdio.h>
#define MAX 16
int main(void)
{
	int num[MAX][MAX]={ };
	double average[MAX];
	double avg_average[MAX];
	int max[MAX];
	int i,j,k,n,m;
	printf("请输入学生人数(1~%d)：",MAX);
	scanf("%d",&m);
	printf("请输入考试科目数(1~%d)",MAX);
	scanf("%d",&n);
	printf("依次输入学号及各科考试成绩：\n\n");
	for(j=0;j<m;j++)
	{
		for(i=0;i<=n;i++)
		{
			scanf("%d",&num[i][j]);
			if(i>0)		average[j]+=num[i][j];
		}
		average[j]/=(i-1);
	 } 
	 puts("--------------------");
	 for(j=0;j<m;j++){
	 	printf("学号：%d\n",num[0][j]);
	 	for(i=1;i<=n;i++){
	 		printf("第%d门科目的考试成绩为:%d\n",i,num[i][j]);
		 }
		 printf("该学生平均成绩为：%.2f\n\n",average[j]);
	 }
	puts("---------------------");
	for(i=1;i<=n;i++)
	{
		for(j=0;j<m;j++)
		{
			avg_average[i]+=num[i][j];
		}
		printf("第%d门课程的平均成绩为%.2f\n",i,avg_average[i]/j);
	}
	for(i=1;i<=n;i++)
	{
		int t = 0;
		max[i]=num[i][0];
		for(j=1;j<m;j++)
		{
			if(max[i]<num[i][j]){
			max[i]=num[i][j];
			t = j;
		}
	}
		 puts("--------------------");
		printf("第%d门课程的最高分为%d，第一名学号为%d",i,max[i],num[0][t]);
	puts("--------------------");
}
}
	
