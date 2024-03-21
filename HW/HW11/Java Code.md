```Java
class Solution {
    public int[][] floodFill(int[][] image, int sr, int sc, int color) {
        boolean [][] visited = new boolean[image.length][image[0].length];
        int orgColor = image[sr][sc];
        bfs(image,sr,sc,color,visited,orgColor);
        return image;
    }
    public static void bfs(int[][] image, int sr, int sc, int color,boolean[][] visited,int orgColor) {
        if(sr<0 ||sc< 0 || sc >= image[0].length || sr >= image.length ||   visited[sr][sc] == true || image[sr][sc] != orgColor) {
            return;
        }
        if(!visited[sr][sc])         {
            image[sr][sc] = color;
            visited[sr][sc] = true;
        }
        bfs(image,sr-1,sc,color,visited,orgColor);
        bfs(image,sr+1,sc,color,visited,orgColor);
        bfs(image,sr,sc-1,color,visited,orgColor);
        bfs(image,sr,sc+1,color,visited,orgColor);

    }
}
```
