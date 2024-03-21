```Python
class Solution:
    def floodFill(self, image, sr, sc, newColor):
        rows = len(image)
        cols = len(image[0])
        visited = [[False for _ in range(cols)] for _ in range(rows)]
        orgColor = image[sr][sc]
        self.bfs(image, sr, sc, newColor, visited, orgColor)
        return image

    def bfs(self, image, sr, sc, newColor, visited, orgColor):
        rows = len(image)
        cols = len(image[0])
        if (sr < 0 or sc < 0 or sc >= cols or sr >= rows or
            visited[sr][sc] or image[sr][sc] != orgColor):
            return
        image[sr][sc] = newColor
        visited[sr][sc] = True
        self.bfs(image, sr - 1, sc, newColor, visited, orgColor)
        self.bfs(image, sr + 1, sc, newColor, visited, orgColor)
        self.bfs(image, sr, sc - 1, newColor, visited, orgColor)
        self.bfs(image, sr, sc + 1, newColor, visited, orgColor)
```
