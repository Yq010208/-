int main(){
	int start_year,start_month,start_day;
	int fin_year,fin_month,fin_day;
	int cutdays,adddays;
	int totaldays=0,yeardays=0;
	int leap;
	printf("请输入您诞生于这个世界年月日，格式为年-月-日\n");
	scanf("%d-%d-%d",&start_year,&start_month,&start_day);
	printf("请输入您此时年月日，格式为年-月-日\n");
	scanf("%d-%d-%d",&fin_year,&fin_month,&fin_day);
	adddays=lastdays(fin_year,fin_month,fin_day);
	cutdays=lastdays(start_year,start_month,start_day);
	//printf("%d\n",cutdays);// for test  需要减去的天数 （出生年开始直到出生时） 
	//printf("%d\n",adddays);// for test   需要加上的天数 （此时年开始直到此时） 
	for(int i=start_year;i<fin_year;i++){
	if(i%4!=0) leap=0;
	else if(i%100!=0) leap=1;
	else if(i%400!=0) leap=0;
	else leap=1;
	if(leap) yeardays+=366;
	else yeardays+=365;
	}
	totaldays=yeardays+adddays-cutdays;
	printf("您已降临这个世界的天数：%d\n",totaldays);//for test （您已降临这个世界的天数）
	int a,b,c;
	a=totaldays%23;
	b=totaldays%28;
	c=totaldays%33;
	if(a<=11)
		printf("您目前的体力处于旺盛期，建议增加户外运动时间！\n");
	else
		printf("您目前的体力比较低迷，建议避免高强度劳动，多加休息！\n");
	if(b<=14)
		printf("您目前的情绪比较高涨，是你大脑的黄金时期，此时学习效果尤为显著！还可以去体验一下具有挑战性项目！\n");
	else
		printf("您目前的情绪比较低迷，不能接受外界的刺激，应当选择适当的方式去放松自己！\n");
	if(c<=16)
		printf("您目前的智力处于黄金时期，此时处理事情和学习正是最好的时机！\n");
	else
	printf("您的智力比较低迷，不适合去处理一些理性的事情，应该去放松自己，让大脑得到一个释放作用！\n");
	system("pause");
}

