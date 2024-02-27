```Python
 def minMeetingRooms(self, intervals: List[List[int]]) -> int:
        if not intervals:
            return 0

        n = len(intervals)
        start_times = sorted(interval[0] for interval in intervals)
        end_times = sorted(interval[1] for interval in intervals)

        min_servers = 0
        end_index = 0

        for start_time in start_times:
            if start_time < end_times[end_index]:
                min_servers += 1  
            else:
                end_index += 1  

        return min_servers
