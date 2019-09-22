#include <iostream>
#include <string>

using namespace std;

class stack
{
private:
	int nArray[10];
	int top;
	string str;
public:
	stack();
	void push(int data);
	int pop();
	void print();
};
stack::stack()
{
	top = -1;
}
void stack::push(int data)
{
	if (top == 9)
	{
		cout << "더이상 들어갈곳이 없습니다!" << endl;
		return;
	}
	nArray[++top] = data;
	cout << nArray[top];
}
int stack::pop()
{
	if (top == -1)
	{
		cout << "스택이 비었습니다!" << endl;
		return 0;
	}
	cout << nArray[top];
	return nArray[top--];
}
void stack::print()
{
	int i;
	for (i = 0; i <= top; i++)
	{
		cout << nArray[i] << " ";
	}cout << endl;
}

int main(int argc, char* argv[])
{
	stack s1;
	string str;
	int X;
	int pushNum = 0;
	string push = "push";
	string pop = "pop ";
	string print = "print ";
	cout << "명령어수 1부터 100000까지 입력: \n";
	cin >> pushNum;
	if (pushNum>100000 && pushNum < 0)
	{
		return -1;
	}
	
	for (int i = 0; i < pushNum; i++)
	{
		cin >> str >> X;
		if (str.compare(push) == 0)
		{
			s1.push(X);
		}
		else if (str.compare(pop) == 0)
		{
			s1.pop();
		}
		else if (str.compare(print) == 0)
		{
			s1.print();
		}
	}


	return 0;
}
