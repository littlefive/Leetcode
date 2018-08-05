# 数独
判断一个 9x9 的数独是否有效。只需要根据以下规则，验证已经填入的数字是否有效即可。

数字 1-9 在每一行只能出现一次。
数字 1-9 在每一列只能出现一次。
数字 1-9 在每一个以粗实线分隔的 3x3 宫内只能出现一次。
```javascript
/**
 * @param {character[][]} board
 * @return {boolean}
 */
var isValidSudoku = function(board) {
  var flag = true;
  for(var i=0; i<9;i++) {
      var obj={};
      if(!flag) {
          break;
      }
      for(var m=0; m<9;m++){
          if(!flag) {
              break;
          }
          if(board[i][m] !== '.'){
              // 横着列判断
              if(board[i].indexOf(board[i][m], m+1) > 0) {
                  flag = false;
              }
          }
             // 竖着列
            // board[0][0]  board[1][0] board[2][0]
          if(board[m][i] !== '.'){
              if(!obj[board[m][i]]) {
                  obj[board[m][i]] = 1;
              } else {
                  flag=false
              }
          }
          
      }
      // 九个格
            var obj1 = {}
            for(var l=0;l<3; l++){
                for(var n=0;n<3;n++){
                    if(board[l + Math.floor(i/3)*3][n+ i%3*3] !== '.') {
                       if(!obj1[board[l + Math.floor(i/3)*3][n+ i%3*3]]){
                           obj1[board[l + Math.floor(i/3)*3][n+ i%3*3]] = 1;
                       } else {
                        flag=false
                       }
                    }
                }
            }
  }  
    return flag
};
```
