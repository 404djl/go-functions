### 1. strings
1. func ContainsRune(s string, r rune) bool  // 属于 strings 包  判断r是否在s中
3. strings.ContainsAny(s, "aeiou")  // 判断s中是否含有"aeiou"中的一种，有返回true

### 2. sort
1. 对二维切片进行自定义排序

   ```go
   package main
   
   import (
   	"fmt"
   	"sort"
   )
   
   func main() {
   	// 示例二维切片
   	nums := [][2]int{
   		{3, 1},
   		{2, 5},
   		{2, 3},
   		{1, 4},
   		{3, 2},
   	}
   
   	// 自定义排序规则
   	sort.Slice(nums, func(i, j int) bool {
   		// 先比较第一个元素，按升序排列
   		if nums[i][0] != nums[j][0] {
   			return nums[i][0] < nums[j][0]
   		}
   		// 当第一个元素相等时，比较第二个元素，按降序排列
   		return nums[i][1] > nums[j][1]
   	})
   
   	// 打印排序结果
   	fmt.Println("排序后:")
   	for _, v := range nums {
   		fmt.Println(v)
   	}
   }
   ```
