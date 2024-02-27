```java
public int minMeetingRooms(int[][] intervals) {
       int n = intervals.length;
    int c = 1;
    int track_endtimes = 0;
    if(n == 0) return 0;
    int [] start_times = new int[n];
    int [] end_times = new int[n];

    for(int i = 0; i < n; i++) {
      start_times[i] = intervals[i][0];
      end_times[i] = intervals[i][1];
    }
    Arrays.sort(start_times);
    Arrays.sort(end_times);
    
    for (int i = 1; i < n; i++ ){
      
        if(start_times[i] < end_times[track_endtimes]){
          c++;
          
        }else{
          track_endtimes++;
        }
      

    }
    return c;
    


    }
