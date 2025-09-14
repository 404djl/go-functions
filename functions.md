### 1. strings

1. func ContainsRune(s string, r rune) bool  // 属于 strings 包  判断r是否在s中
2. strings.ContainsAny(s, "aeiou")  // 判断s中是否含有"aeiou"中的一种，有返回true
3. strings.ToLower(s) 将大写字母转换成小写字母
4. strings.NewReplacer是 `strings` 包提供的一个函数，用于创建一个**字符串替换器（Replacer）**，专门用于高效地执行**多组字符串替换操作**。
   1. **创建替换器**：通过 `strings.NewReplacer(old1, new1, old2, new2, ...)` 定义替换规则（参数必须是成对的旧值和新值）
   2. **执行替换**：调用替换器的 `Replace(s)` 方法，对字符串 `s` 执行所有定义的替换

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

### 3. slices

1. slices.Backward(切片)，从后往前遍历包括下标

### 4. math

1. int(math.Sqrt(float64(n)))
