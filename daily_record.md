struct request {
	int dev;		/* -1 if no request */
	int cmd;		/* READ or WRITE */
	int errors;
	unsigned long sector;
	unsigned long nr_sectors;
	char * buffer;
	struct task_struct * waiting;
	struct buffer_head * bh;
	struct request * next;
};

------

struct task_struct {
/* these are hardcoded - don't touch */
	long state;	/* -1 unrunnable, 0 runnable, >0 stopped */
	long counter;
	long priority;
	long signal;
	struct sigaction sigaction[32];
	long blocked;	/* bitmap of masked signals */
/* various fields */
	int exit_code;
	unsigned long start_code,end_code,end_data,brk,start_stack;
	long pid,father,pgrp,session,leader;
	unsigned short uid,euid,suid;
	unsigned short gid,egid,sgid;
	long alarm;
	long utime,stime,cutime,cstime,start_time;
	unsigned short used_math;
/* file system info */
	int tty;		/* -1 if no tty, so it must be signed */
	unsigned short umask;
	struct m_inode * pwd;
	struct m_inode * root;
	struct m_inode * executable;
	unsigned long close_on_exec;
	struct file * filp[NR_OPEN];
/* ldt for this task 0 - zero 1 - cs 2 - ds&ss */
	struct desc_struct ldt[3];
/* tss for this task */
	struct tss_struct tss;
};

------

![image-20220331203428681](/home/tong/.config/Typora/typora-user-images/image-20220331203428681.png)

![image-20220331203516868](/home/tong/.config/Typora/typora-user-images/image-20220331203516868.png)

![image-20220331204510406](/home/tong/.config/Typora/typora-user-images/image-20220331204510406.png)

![image-20220331204620392](/home/tong/.config/Typora/typora-user-images/image-20220331204620392.png)

![image-20220331204714825](/home/tong/.config/Typora/typora-user-images/image-20220331204714825.png)![image-20220331205053733](/home/tong/.config/Typora/typora-user-images/image-20220331205053733.png)

![image-20220331205612961](/home/tong/.config/Typora/typora-user-images/image-20220331205612961.png)

![image-20220331212039738](/home/tong/.config/Typora/typora-user-images/image-20220331212039738.png)

![image-20220331212134377](/home/tong/.config/Typora/typora-user-images/image-20220331212134377.png)

![image-20220331212342731](/home/tong/.config/Typora/typora-user-images/image-20220331212342731.png)

![image-20220331233853741](/home/tong/.config/Typora/typora-user-images/image-20220331233853741.png)

![image-20220401231743288](/home/tong/.config/Typora/typora-user-images/image-20220401231743288.png)

![image-20220401234112335](/home/tong/.config/Typora/typora-user-images/image-20220401234112335.png)

![image-20220402210520688](/home/tong/.config/Typora/typora-user-images/image-20220402210520688.png)

![image-20220402210954107](/home/tong/.config/Typora/typora-user-images/image-20220402210954107.png)

![image-20220402211032908](/home/tong/.config/Typora/typora-user-images/image-20220402211032908.png)

![image-20220402211107676](/home/tong/.config/Typora/typora-user-images/image-20220402211107676.png)

![image-20220402211320229](/home/tong/.config/Typora/typora-user-images/image-20220402211320229.png)

![image-20220402211516349](/home/tong/.config/Typora/typora-user-images/image-20220402211516349.png)

![image-20220402214414470](/home/tong/.config/Typora/typora-user-images/image-20220402214414470.png)

![image-20220402221810343](/home/tong/.config/Typora/typora-user-images/image-20220402221810343.png)

![image-20220402222620196](/home/tong/.config/Typora/typora-user-images/image-20220402222620196.png)

![image-20220402223610314](/home/tong/.config/Typora/typora-user-images/image-20220402223610314.png)

![image-20220402223712213](/home/tong/.config/Typora/typora-user-images/image-20220402223712213.png)

## ![image-20220402223742097](/home/tong/.config/Typora/typora-user-images/image-20220402223742097.png)

![image-20220402223806710](/home/tong/.config/Typora/typora-user-images/image-20220402223806710.png)

![image-20220402223846403](/home/tong/.config/Typora/typora-user-images/image-20220402223846403.png)

![image-20220403005349843](/home/tong/.config/Typora/typora-user-images/image-20220403005349843.png)

![image-20220403005922383](/home/tong/.config/Typora/typora-user-images/image-20220403005922383.png)

![image-20220403010128314](/home/tong/.config/Typora/typora-user-images/image-20220403010128314.png)

![image-20220403010246964](/home/tong/.config/Typora/typora-user-images/image-20220403010246964.png)

![image-20220403015207785](/home/tong/.config/Typora/typora-user-images/image-20220403015207785.png)

![image-20220403015501876](/home/tong/.config/Typora/typora-user-images/image-20220403015501876.png)

![image-20220403215912443](/home/tong/.config/Typora/typora-user-images/image-20220403215912443.png)

![image-20220403221627922](/home/tong/.config/Typora/typora-user-images/image-20220403221627922.png)

![image-20220403221948091](/home/tong/.config/Typora/typora-user-images/image-20220403221948091.png)

![image-20220403223906252](/home/tong/.config/Typora/typora-user-images/image-20220403223906252.png)

![image-20220404000659187](/home/tong/.config/Typora/typora-user-images/image-20220404000659187.png)

![image-20220404001302427](/home/tong/.config/Typora/typora-user-images/image-20220404001302427.png)

![image-20220404003349146](/home/tong/.config/Typora/typora-user-images/image-20220404003349146.png)

![image-20220404091352222](/home/tong/.config/Typora/typora-user-images/image-20220404091352222.png)

![image-20220404110127069](/home/tong/.config/Typora/typora-user-images/image-20220404110127069.png)

![image-20220404110212476](/home/tong/.config/Typora/typora-user-images/image-20220404110212476.png)

![image-20220404115728562](/home/tong/.config/Typora/typora-user-images/image-20220404115728562.png)

![image-20220404120157271](/home/tong/.config/Typora/typora-user-images/image-20220404120157271.png)

![image-20220404121326815](/home/tong/.config/Typora/typora-user-images/image-20220404121326815.png)

![image-20220404124917345](/home/tong/.config/Typora/typora-user-images/image-20220404124917345.png)

![image-20220404125409451](/home/tong/.config/Typora/typora-user-images/image-20220404125409451.png)

![image-20220404125943831](/home/tong/.config/Typora/typora-user-images/image-20220404125943831.png)

![image-20220404130121879](/home/tong/.config/Typora/typora-user-images/image-20220404130121879.png)

![image-20220404130749757](/home/tong/.config/Typora/typora-user-images/image-20220404130749757.png)

![image-20220404132709640](/home/tong/.config/Typora/typora-user-images/image-20220404132709640.png)

![image-20220404133048720](/home/tong/.config/Typora/typora-user-images/image-20220404133048720.png)

![image-20220404134610178](/home/tong/.config/Typora/typora-user-images/image-20220404134610178.png)

![image-20220404140121215](/home/tong/.config/Typora/typora-user-images/image-20220404140121215.png)

![image-20220404140426384](/home/tong/.config/Typora/typora-user-images/image-20220404140426384.png)

![image-20220404140838270](/home/tong/.config/Typora/typora-user-images/image-20220404140838270.png)

![image-20220404141233357](/home/tong/.config/Typora/typora-user-images/image-20220404141233357.png)

![image-20220404144518352](/home/tong/.config/Typora/typora-user-images/image-20220404144518352.png)

![image-20220404150033423](/home/tong/.config/Typora/typora-user-images/image-20220404150033423.png)

![image-20220404150121679](/home/tong/.config/Typora/typora-user-images/image-20220404150121679.png)

![image-20220404150349385](/home/tong/.config/Typora/typora-user-images/image-20220404150349385.png)

![image-20220404205910166](/home/tong/.config/Typora/typora-user-images/image-20220404205910166.png)

![image-20220404210045910](/home/tong/.config/Typora/typora-user-images/image-20220404210045910.png)s

![image-20220404214110647](/home/tong/.config/Typora/typora-user-images/image-20220404214110647.png)

![image-20220404231758868](/home/tong/.config/Typora/typora-user-images/image-20220404231758868.png)

![image-20220405094134018](/home/tong/.config/Typora/typora-user-images/image-20220405094134018.png)

![image-20220405094519689](/home/tong/.config/Typora/typora-user-images/image-20220405094519689.png)

![image-20220405094653554](/home/tong/.config/Typora/typora-user-images/image-20220405094653554.png)

![image-20220405094751115](/home/tong/.config/Typora/typora-user-images/image-20220405094751115.png)

![image-20220405094843044](/home/tong/.config/Typora/typora-user-images/image-20220405094843044.png)

![image-20220405095227858](/home/tong/.config/Typora/typora-user-images/image-20220405095227858.png)

![image-20220405101123654](/home/tong/.config/Typora/typora-user-images/image-20220405101123654.png)

![image-20220405202405785](/home/tong/.config/Typora/typora-user-images/image-20220405202405785.png)

![image-20220405202659768](/home/tong/.config/Typora/typora-user-images/image-20220405202659768.png)

![image-20220405225840774](/home/tong/.config/Typora/typora-user-images/image-20220405225840774.png)