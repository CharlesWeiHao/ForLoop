# ForLoop
优化for循环的两种方式

        // 题目：for循环
        //        for (int i = 0; i < 1000; i++) {
        //            for (int j = 0; j < 100; j++) {
        //                for (int k = 0; k < 10; k++) {
        //                    NSLog(@"i->%d -- j->%d -- k->%d",i,j,k);
        //                }
        //            }
        //        }
        
        // start time: 17:17:10.582027+0800
        // end   time: 17:18:25.039112+0800
        // Time difference: 1:15
        
        
        // 优化方法1：把循环次数多的放到内部，循环次数少的放在最外层
        //        for (int k = 0; k < 1000; k++) {
        //            for (int j = 0; j < 100; j++) {
        //                for (int i = 0; i < 10; i++) {
        //                    NSLog(@"k->%d /nj->%d/ni->%d",k,j,i);
        //                }
        //            }
        //        }
        
        // start time: 17:19:28.703301+0800
        // end   time: 17:19:56.295733+0800
        // Time difference: 27.592432
        
        // 优化方法2：把默认初始化的值，单独提取出来
        int k, j, i;
        for (k = 0; k < 1000; k++) {
            for (j = 0; j < 100; j++) {
                for (i = 0; i < 10; i++) {
                    NSLog(@"k->%d /nj->%d/ni->%d",k,j,i);
                }
            }
        }
        
        // start time: 17:20:43.146741+0800
        // end   time: 17:21:10.422901+0800
        // Time difference: 27.276160
