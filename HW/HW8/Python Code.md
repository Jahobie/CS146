```Python
  
  def longestPalindrome(self, s):
        frequency_map = {}
        for ch in s:
            if ch.isalpha():
                frequency_map[ch] = frequency_map.get(ch, 0) + 1

        length = 0
        has_odd_frequency = False
        for count in frequency_map.values():
            length += count
            if count % 2 != 0:
                has_odd_frequency = True
                length -= 1

        if has_odd_frequency:
            length += 1

        return length
