数组
1)长度 length
var arr = [1, 2, 3.14, 'Hello', null, true];
arr.length; // 6
请注意，直接给Array的length赋一个新的值会导致Array大小的变化：

var arr = [1, 2, 3];
arr.length; // 3
arr.length = 6;
arr; // arr变为[1, 2, 3, undefined, undefined, undefined]
arr.length = 2;
arr; // arr变为[1, 2]
Array可以通过索引把对应的元素修改为新的值，因此，对Array的索引进行赋值会直接修改这个Array：

var arr = ['A', 'B', 'C'];
arr[1] = 99;
arr; // arr现在变为['A', 99, 'C']
请注意，如果通过索引赋值时，索引超过了范围，同样会引起Array大小的变化：

var arr = [1, 2, 3];
arr[5] = 'x';
arr; // arr变为[1, 2, 3, undefined, undefined, 'x']


2)indexOf