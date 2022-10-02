# Leetcode
Решая задачи на литкоде можно столкнуться с множеством проблем. Например, мне потребовалось не мало времени, чтобы поянть, чт без конструкций `def` и `class` на литкоде задачи не решаются
Холтя решение полностью рабочее(мне советовали поработать с форматом вывода, версией питона, все было верно)
### Проблема `Time Limit Exceeded`

Полностью рабочий код:
```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        sol = []
        print("Input nums:")

        count = 0

        print("Target:")
        
        for i in range(len(nums)):
            for b in range(len(nums)):
                if nums[i] + nums[b] == target and count != 1 and i!=b:
                    sol.append(i)
                    sol.append(b)
                    
                    count += 1

        return sol
```
Но Литкод ругается на долгое выполнение кода.
Я нашел другое решение, которое проходит на литкоде, но, которое я не совсем понял

```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:

        ans = []
        for i in range(len(nums)):

            if target - nums[i] in nums:

                ind = nums.index(target - nums[i])
                if i == ind:
                    continue
                if i in ans and ind in ans:
                    continue
                ans.append(i)
                ans.append(ind)

        ans.sort()
        return ans
```
Первые две строки не обязательны

Решение от литкода, которое тоже не прошло(Time limit exceeded):

```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[j] == target - nums[i]:
                    return [i, j]
```
