```cpp
#include <iostream>

int main(){
	int a, b, result;
	char op;

	while(true){
		//====================solution 1====================
		std::cout << "Please enter operator first: " << std::endl;
		std::cin >> op;
		//这里即使输入q还是会继续输入a和b，因为代码是顺序执行，没有做”提前退出“
		std::cout << "Please enter a:" << std::endl;
		std::cin >> a;
		std::cout << "Please enter b: " << std::endl;
		std::cin >> b;
		if(op == 'q'){
			break;
		}
		else if(op == '+'){
			result = a + b;
			std::cout << "The result is: " << result << std::endl;
		}
		else if(op == '-'){
			result = a - b;
			std::cout << "The result is: " << result << std::endl;
		}
		else{
			std::cout << "I don't know this operator yet now" << std::endl;
		}

		//====================solution 2====================
		//嵌套太多了，不美观不清晰
		std::cout << "Please enter operator first: " << std::endl;
		std::cin >> op;
		
		if(op == 'q'){
			break;
		}
		else{
			std::cout << "Please enter a:" << std::endl;
			std::cin >> a;
			std::cout << "Please enter b: " << std::endl;
			std::cin >> b;
			if(op == '+'){
				result = a + b;
				std::cout << "The result is: " << result << std::endl;
			}
			else if(op == '-'){
				result = a - b;
				std::cout << "The result is: " << result << std::endl;
			}
			else{
				std::cout << "I don't know this operator yet now" << std::endl;
			}
		}
		
		  
		
		//====================solution 3====================
		// 1. 先问操作符
		std::cout << "Please enter operator (+, -, or q to quit): " << std::endl;
		std::cin >> op;

		// 2. 检查是否要退出
		if (op == 'q') {
			std::cout << "Goodbye!" << std::endl;
			break; // 关键！这会立刻跳出 while 循环
		}

		// 3. 如果没退出，说明是运算符号。继续问数字
		std::cout << "Please enter a: " << std::endl;
		std::cin >> a;
		std::cout << "Please enter b: " << std::endl;
		std::cin >> b;
		if(op == '+'){
			result = a + b;
		}
		else if(op == '-'){
			result = a - b;
		}
		else{
			std::cout << "I don't know this operator yet now" << std::endl;
			continue;
		}

		std::cout << "The result is: " << result << std::endl;
	}
	return 0;
}
```
