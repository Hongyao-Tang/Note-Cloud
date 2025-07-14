

S - 并发编程，IO密集型任务，阻塞不让其他任务进行

T

- 协程，能挂起，让其他协程运行/不阻塞其他协程
- 运行哪个新的协程，当前协程IO完成怎么处理：调度器

A - 关键字编写像同步代码的异步代码

- async def 声明函数为异步函数/协程，执行可以被恢复暂停
- 协程调用不会立即执行，返回一个协程对象，通过事件循环运行
```py
async def fetch_data():
    pass
```

- await 用于协程内部，挂起协程，等待后面的IO任务完成
- asyncio.sleep(2) 模拟一个异步IO操作
```py
from datetime import datetime
import asyncio

async def fetch_data():
    print("Before fetching: ", datetime.now())
    await asyncio.sleep(2)
    print("After fetching: ", datetime.now())
```

- asyncio.run() 启动事件循环
```py
asyncio.run(fetch_data())
```
