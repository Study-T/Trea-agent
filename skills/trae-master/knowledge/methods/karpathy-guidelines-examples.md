# Examples
# 示例

Real-world code examples demonstrating the four principles. Each example shows what LLMs commonly do wrong and how to fix it.
实际代码示例，展示四个原则。每个示例展示LLM常犯的错误以及如何修复。

---

## 1. Think Before Coding Examples
## 1. 编码前先思考示例

### Example 1: Hidden Assumptions
### 示例1：隐藏的假设

**User Request / 用户请求**: "Add a feature to export user data"
**用户请求**: "添加导出用户数据的功能"

❌ **What LLMs Do (Wrong Assumptions) / LLM常做的（错误假设）**:
```python
def export_users(format='json'):
    """Export all users"""
    users = User.objects.all()
    if format == 'json':
        return JsonResponse({'users': list(users.values())})
    elif format == 'csv':
        # CSV export logic...
        pass
```

✅ **What to Do Instead / 应该怎么做**:
```python
# First, ask clarifying questions / 首先，澄清问题
"""
Before implementing, I need to clarify:

1. What format do you need? (JSON, CSV, XML, etc.)
2. Should we export all users or filter by criteria?
3. What fields should be included?
4. Should this be a file download or API response?

Please let me know your preferences.
"""
```

---

### Example 2: Silent Decision Making
### 示例2：沉默决策

**User Request / 用户请求**: "Add user authentication"
**用户请求**: "添加用户认证"

❌ **What LLMs Do (Without Asking) / LLM常做的（不问就做）**:
```python
# Assumed JWT is the right choice
# 假设 JWT 是正确的选择
auth = JWTAuth(algorithm='HS256', expiry=3600)
```

✅ **What to Do Instead / 应该怎么做**:
```python
# Present options before deciding / 做决定前先展示选项
"""
For user authentication, I see a few options:

1. **Session-based** - Traditional server sessions
2. **JWT** - Stateless tokens, good for APIs
3. **OAuth** - Third-party login (Google, GitHub, etc.)

Which approach fits your use case? Or would you like me to recommend one based on your setup?
"""
```

---

## 2. Simplicity First Examples
## 2. 简单性优先示例

### Example 1: Over-abstraction
### 示例1：过度抽象

**User Request / 用户请求**: "Create a utility to format dates"
**用户请求**: "创建一个格式化日期的工具"

❌ **What LLMs Do (Over-engineered) / LLM常做的（过度设计）**:
```python
class DateFormatter:
    """A flexible date formatting utility"""

    def __init__(self, locale='en', timezone=None, format_type='default'):
        self.locale = locale
        self.timezone = timezone
        self.format_type = format_type
        self.config = self._load_config()

    def _load_config(self):
        # Load configuration...
        return {}

    def format(self, date, custom_format=None):
        # Complex formatting logic...
        pass

    def parse(self, date_string):
        # Parsing logic...
        pass

class DateFormatterSingleton(DateFormatter):
    # Singleton pattern...
    pass
```

✅ **What to Do Instead / 应该怎么做**:
```python
# Just what you need / 只写你需要的
def format_date(date, fmt='%Y-%m-%d'):
    """Format a date object as string."""
    return date.strftime(fmt)

# Or if user needs more / 或者如果用户需要更多
def format_date(date, locale='en'):
    """Format a date for the given locale."""
    if locale == 'en':
        return date.strftime('%B %d, %Y')  # "January 15, 2024"
    elif locale == 'zh':
        return date.strftime('%Y年%m月%d日')
    return str(date)
```

---

### Example 2: Speculative Features
### 示例2：投机性功能

**User Request / 用户请求**: "Write a function to validate email"
**用户请求**: "写一个验证邮箱的函数"

❌ **What LLMs Do (Adding Speculation) / LLM常做的（添加投机功能）**:
```python
def validate_email(email, check_mx=False, check_disposable=False,
                  check_role=False, min_length=5, max_length=254):
    """
    Validate email with multiple options.

    Args:
        check_mx: Check if domain has MX record
        check_disposable: Reject disposable emails
        check_role: Reject role-based emails (info@, admin@)
        min_length: Minimum email length
        max_length: Maximum email length
    """
    # 200 lines of validation logic...
```

✅ **What to Do Instead / 应该怎么做**:
```python
def validate_email(email):
    """Validate email format."""
    import re
    pattern = r'^[\w\.-]+@[\w\.-]+\.\w+$'
    return bool(re.match(pattern, email))

# If user asks for MX check later, add it then / 如果用户之后要求MX检查，再加
```

---

## 3. Surgical Changes Examples
## 3. 精准修改示例

### Example 1: Unnecessary File Rewrite
### 示例1：不必要的文件重写

**User Request / 用户请求**: "Add input sanitization to the user form"
**用户请求**: "在用户表单中添加输入清理"

❌ **What LLMs Do (Rewrite Entire File) / LLM常做的（重写整个文件）**:
```python
# Entire 500-line file rewritten just to add one function call
# 为了添加一个函数调用重写了整个500行的文件

def process_form(request):
    # ... 500 lines of code ...
    # Add just one line:
    name = sanitize_input(request.POST.get('name'))
    # ... another 500 lines ...
```

✅ **What to Do Instead / 应该怎么做**:
```python
# Just find and modify what needs to be modified / 只找到并修改需要修改的地方

# Find this specific function and add the sanitization
def process_form(request):
    name = request.POST.get('name')
+   name = sanitize_input(name)  # Added input sanitization
    email = request.POST.get('email')
    # Only modify what needs to be modified
```

---

### Example 2: Changing Unrelated Code
### 示例2：修改无关代码

**User Request / 用户请求**: "Add retry logic to the API client"
**用户请求**: "给API客户端添加重试逻辑"

❌ **What LLMs Do (Affects Everything) / LLM常做的（影响一切）**:
```python
# In api_client.py (1000 lines)
# Changed 500 lines including unrelated code
# 修改了包括无关代码在内的500行

class APIClient:
    def __init__(self):
        self.retry_count = 3
        # ... many unrelated changes ...
```

✅ **What to Do Instead / 应该怎么做**:
```python
# Only touch the specific method / 只修改特定方法
class APIClient:
    def __init__(self):
        pass  # Don't change existing init

    def make_request(self, url):
+       for attempt in range(3):
+           try:
+               return self._do_request(url)
+           except Exception as e:
+               if attempt == 2:
+                   raise
+               continue
-       # Rest of class unchanged / 其余不变
```

---

## 4. Goal-Driven Examples
## 4. 目标驱动示例

### Example 1: Unclear Success Criteria
### 示例1：成功标准不清晰

**User Request / 用户请求**: "Improve the code"
**用户请求**: "改进代码"

❌ **What LLMs Do (Vague Goal) / LLM常做的（模糊目标）**:
```python
# Refactored everything, added patterns, improved structure
# But user wanted something specific
# 重构了一切，添加了模式，改进了结构
# 但用户想要的是具体的东西
```

✅ **What to Do Instead / 应该怎么做**:
```python
# Before starting, clarify the goal / 开始前，澄清目标
"""
I'd like to help improve the code, but I need to understand your goal:

1. Are you looking for:
   - Better performance?
   - Easier maintenance?
   - Bug fixes?
   - Security improvements?

2. What does "success" look like for this task?

Please let me know your specific objectives.
"""
```

---

### Example 2: Missing Verification
### 示例2：缺少验证

**User Request / 用户请求**: "Add rate limiting to the API"
**用户请求**: "给API添加速率限制"

❌ **What LLMs Do (No Verification) / LLM常做的（没有验证）**:
```python
# Implemented rate limiting
# No tests, no verification steps
# 实现了速率限制
# 没有测试，没有验证步骤
```

✅ **What to Do Instead / 应该怎么做**:
```python
# Add verification / 添加验证
def test_rate_limiting():
    """Test rate limiting functionality."""

    # Test: Rate limits apply to /users and /posts
    # 测试：速率限制适用于 /users 和 /posts
    response = make_request('/users', count=100)
    assert response.status == 429  # Rate limited

    # Test: Existing endpoint tests still pass
    # 测试：现有端点测试仍然通过
    response = make_request('/health')
    assert response.status == 200

    # Test: Rate limit persists across app restarts
    # 测试：速率限制在应用重启后持续存在
```

---

## Summary of Common Mistakes
## 常见错误总结

| Principle | Common Mistake | Fix |
|-----------|----------------|-----|
| Think First | Assuming requirements | Ask clarifying questions first |
| Simplicity | Over-abstraction | Write minimum code needed |
| Surgical | Rewriting too much | Make smallest possible change |
| Goal-Driven | Unclear success criteria | Define what "done" looks like |
