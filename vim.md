## 一、100 个指令按学习阶段排序

### 第一阶段：基础生存（掌握前 30 个即可日常使用）
1. `i` – 插入  
2. `Esc` – 返回普通模式  
3. `h` / `j` / `k` / `l` – 左下上右  
4. `:w` – 保存  
5. `:q` – 退出  
6. `:wq` / `ZZ` – 保存退出  
7. `:q!` – 强制退出  
8. `x` – 删除字符  
9. `dd` – 删除行  
10. `u` – 撤销  
11. `Ctrl+r` – 重做  
12. `yy` – 复制行  
13. `p` – 粘贴  
14. `gg` – 文件首行  
15. `G` – 文件末行  
16. `0` – 行首  
17. `$` – 行尾  
18. `w` / `b` – 单词跳转  
19. `/pattern` + `n` / `N` – 查找  
20. `:s/old/new` – 替换  
21. `:%s/old/new/g` – 全文件替换  
22. `o` / `O` – 上下新行  
23. `a` / `A` – 行尾插入  
24. `v` – 可视模式  
25. `V` – 可视行模式  
26. `.` – 重复上次操作  
27. `J` – 合并行  
28. `r` – 替换字符  
29. `~` – 切换大小写  
30. `>>` / `<<` – 缩进  

### 第二阶段：日常提效（31–70）
31. `I` – 行首插入  
32. `^` – 行首非空字符  
33. `e` / `ge` – 单词尾  
34. `nG` – 跳转某行  
35. `Ctrl+u` / `Ctrl+d` – 半页翻  
36. `Ctrl+f` / `Ctrl+b` – 整页翻  
37. `H` / `M` / `L` – 屏幕位置  
38. `{` / `}` – 段落跳转  
39. `%` – 括号匹配  
40. `X` – 删除前字符  
41. `dw` / `db` – 删单词  
42. `d$` / `D` – 删至行尾  
43. `d0` – 删至行首  
44. `yw` – 复制单词  
45. `y$` – 复制至行尾  
46. `P` – 粘贴在前  
47. `cc` – 删行并插入  
48. `cw` – 删单词并插入  
49. `C` – 删至行尾并插入  
50. `s` / `S` – 删字符/行并插入  
51. `==` – 自动缩进行  
52. `?pattern` – 向上查找  
53. `*` / `#` – 查光标词  
54. `:s/old/new/g` – 行内全换  
55. `:%s/old/new/gc` – 确认替换  
56. `:e filename` – 切换文件  
57. `:bn` / `:bp` – 切换缓冲区  
58. `:ls` – 列表缓冲区  
59. `:bd` – 关闭缓冲区  
60. `:sp` – 水平分屏  
61. `:vsp` – 垂直分屏  
62. `Ctrl+w w` – 切换窗口  
63. `Ctrl+w h/j/k/l` – 方向切窗口  
64. `Ctrl+w =` – 均分窗口  
65. `Ctrl+w _` – 最大高度  
66. `Ctrl+w |` – 最大宽度  
67. `:tabnew` – 新建标签  
68. `gt` / `gT` – 切换标签  
69. `:saveas filename` – 另存为  
70. `Ctrl+g` – 显示文件信息  

### 第三阶段：高阶自动化（71–100）
71. `q[a-z]` – 开始录宏  
72. `q` – 停止宏  
73. `@[a-z]` – 执行宏  
74. `:reg` – 查看寄存器  
75. `"*y` / `"*p` – 系统剪贴板  
76. `:edit` / `:e!` – 重新加载  
77. `Ctrl+v` – 可视块模式  
78. `R` – 替换模式  
79. `ZZ` – 保存退出（已有）  
80. `[count]` 前缀（如 `3dd`）  
81. 组合命令（如 `dG` 删到末尾）  
82. `:!command` – 执行外部命令（增加，高频）  
83. `:%!sort` – 过滤排序（增）  
84. `gf` – 跳转到光标下文件（增）  
85. `Ctrl+o` / `Ctrl+i` – 跳转历史（增）  
86. `ga` – 显示字符编码（增）  
87. `gU` / `gu` – 大写/小写单词（增）  
88. `zf` – 折叠（增）  
89. `zo` / `zc` – 开/关折叠（增）  
90. `:set number` – 显示行号（增）  
91. `:nohlsearch` – 取消高亮（增）  
92. `K` – 查看 man（增）  
93. `:!python %` – 运行脚本（增）  
94. `Ctrl+a` – 数字+1（增）  
95. `Ctrl+x` – 数字−1（增）  
96. `g;` / `g,` – 跳修改位置（增）  
97. `:normal` – 批量执行普通命令（增）  
98. `:g/pattern/d` – 删除匹配行（增）  
99. `:v/pattern/d` – 保留匹配行（增）  
100. `:help` – 永远的好朋友  

---




```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
Vim 大师训练营 - 三阶段完整版
第一阶段：基础生存 (1-30)
第二阶段：日常提效 (31-70)
第三阶段：高阶自动化 (71-100)
总计：100个核心指令
"""

import random
import sys
import os
import json
from datetime import datetime
from collections import defaultdict

class VimGrandMaster:
    def __init__(self):
        # ========== 第一阶段：基础生存 (1-30) ==========
        self.stage1 = {
            'i': '进入插入模式（光标前插入）',
            'Esc': '返回普通模式',
            'h': '光标左移', 'j': '光标下移', 'k': '光标上移', 'l': '光标右移',
            'gg': '移动到文件首行', 'G': '移动到文件末行',
            '0': '移动到行首', '$': '移动到行尾',
            'w': '下一个单词开头', 'b': '上一个单词开头',
            'x': '删除光标下字符', 'dd': '删除当前行',
            'yy': '复制当前行', 'p': '光标后粘贴',
            'u': '撤销', 'Ctrl+r': '重做',
            ':w': '保存文件', ':q': '退出Vim',
            ':wq': '保存并退出', 'ZZ': '保存并退出',
            ':q!': '强制退出不保存',
            '/pattern': '正向搜索', 'n': '下一个匹配', 'N': '上一个匹配',
            ':s/old/new': '当前行替换首个',
            ':%s/old/new/g': '全文件替换',
            'o': '下方插入新行', 'O': '上方插入新行',
            'a': '光标后插入', 'A': '行尾插入',
            'v': '可视模式', 'V': '可视行模式',
            '.': '重复上次操作', 'J': '合并行',
            'r': '替换字符', '~': '切换大小写',
            '>>': '增加缩进', '<<': '减少缩进',
        }
        
        # ========== 第二阶段：日常提效 (31-70) ==========
        self.stage2 = {
            'I': '行首插入', '^': '行首非空字符',
            'e': '单词结尾', 'ge': '上一个单词结尾',
            'nG': '跳转到第n行（如5G）',
            'Ctrl+u': '向上半页', 'Ctrl+d': '向下半页',
            'Ctrl+f': '向下整页', 'Ctrl+b': '向上整页',
            'H': '屏幕顶部', 'M': '屏幕中部', 'L': '屏幕底部',
            '{': '上一段落', '}': '下一段落',
            '%': '括号匹配',
            'X': '删除前字符', 'dw': '删除单词', 'db': '删除到单词首',
            'd$': '删除到行尾', 'D': '删除到行尾',
            'd0': '删除到行首',
            'yw': '复制单词', 'y$': '复制到行尾',
            'P': '光标前粘贴',
            'cc': '删除行并插入', 'cw': '删除单词并插入',
            'C': '删除到行尾并插入', 's': '删除字符并插入',
            'S': '删除行并插入',
            '==': '自动缩进行',
            '?pattern': '向上搜索',
            '*': '向下搜索光标词', '#': '向上搜索光标词',
            ':s/old/new/g': '行内全替换',
            ':%s/old/new/gc': '全局确认替换',
            ':e filename': '切换文件', ':bn': '下一缓冲区',
            ':bp': '上一缓冲区', ':ls': '列出缓冲区',
            ':bd': '关闭缓冲区',
            ':sp': '水平分屏', ':vsp': '垂直分屏',
            'Ctrl+w w': '切换窗口',
            'Ctrl+w h/j/k/l': '方向切换窗口',
            'Ctrl+w =': '均分窗口', 'Ctrl+w _': '最大高度',
            'Ctrl+w |': '最大宽度',
            ':tabnew': '新建标签', 'gt': '下一标签',
            'gT': '上一标签', ':saveas': '另存为',
            'Ctrl+g': '文件信息',
        }
        
        # ========== 第三阶段：高阶自动化 (71-100) ==========
        self.stage3 = {
            # 宏录制与回放 (71-73)
            'q[a-z]': '开始录制宏到寄存器（如qa）',
            'q': '停止录制宏',
            '@[a-z]': '执行宏（如@a）',
            
            # 寄存器与系统剪贴板 (74-75)
            ':reg': '查看所有寄存器内容',
            '"*y': '复制到系统剪贴板', '"*p': '从系统剪贴板粘贴',
            
            # 文件操作 (76)
            ':edit': '重新加载当前文件', ':e!': '强制重新加载放弃修改',
            
            # 可视块模式 (77)
            'Ctrl+v': '进入可视块模式（列编辑）',
            
            # 替换模式 (78)
            'R': '进入替换模式（覆盖输入）',
            
            # 组合命令 (80-81)
            '[count]': '数字前缀（如3dd删除3行）',
            '组合命令': '复合操作（如dG删除到末尾，y$复制到行尾）',
            
            # 外部命令 (82-83)
            ':!command': '执行外部命令（如:!ls）',
            ':%!sort': '用外部命令过滤文件内容（排序）',
            
            # 文件与跳转 (84-86)
            'gf': '跳转到光标下的文件',
            'Ctrl+o': '跳回之前位置', 'Ctrl+i': '跳到之后位置',
            'ga': '显示光标下字符的ASCII/Unicode编码',
            
            # 大小写转换 (87)
            'gU': '将单词转为大写（如gUw）', 'gu': '将单词转为小写（如guw）',
            
            # 代码折叠 (88-89)
            'zf': '创建折叠', 'zo': '打开折叠', 'zc': '关闭折叠',
            
            # 显示设置 (90-91)
            ':set number': '显示行号', ':set nonumber': '隐藏行号',
            ':nohlsearch': '取消搜索高亮',
            
            # 帮助与文档 (92)
            'K': '查看光标下单词的man手册',
            
            # 运行脚本 (93)
            ':!python %': '运行当前Python脚本（可换成其他语言）',
            
            # 数字增减 (94-95)
            'Ctrl+a': '光标下数字+1', 'Ctrl+x': '光标下数字-1',
            
            # 修改历史跳转 (96)
            'g;': '跳转到上一个修改位置', 'g,': '跳转到下一个修改位置',
            
            # 批量执行 (97)
            ':normal': '批量执行普通模式命令（如:normal i//）',
            
            # 全局命令 (98-99)
            ':g/pattern/d': '删除所有匹配pattern的行',
            ':v/pattern/d': '删除所有不匹配pattern的行（保留匹配行）',
            
            # 终极帮助 (100)
            ':help': '打开Vim帮助文档', ':help topic': '查看特定主题帮助',
        }
        
        # 合并所有指令
        self.all_commands = {**self.stage1, **self.stage2, **self.stage3}
        
        # 指令列表
        self.stage1_list = list(self.stage1.keys())
        self.stage2_list = list(self.stage2.keys())
        self.stage3_list = list(self.stage3.keys())
        
        # 统计数据
        self.stats = defaultdict(lambda: {'correct': 0, 'wrong': 0, 'hint_used': 0, 'last_practiced': None})
        self.session_stats = {'total': 0, 'correct': 0, 'start_time': datetime.now()}
        
        # 加载历史数据
        self.load_stats()
    
    def load_stats(self):
        """加载历史练习数据"""
        try:
            with open('vim_grandmaster_stats.json', 'r') as f:
                data = json.load(f)
                for cmd, stat in data.items():
                    self.stats[cmd] = stat
        except FileNotFoundError:
            pass
    
    def save_stats(self):
        """保存练习数据"""
        # 转换defaultdict为普通dict
        save_data = {k: dict(v) for k, v in self.stats.items()}
        with open('vim_grandmaster_stats.json', 'w') as f:
            json.dump(save_data, f, indent=2)
    
    def print_header(self, stage_name):
        """打印头部信息"""
        os.system('clear' if os.name == 'posix' else 'cls')
        print("=" * 75)
        print(f"   🏆 Vim 大师训练营 - {stage_name}")
        print("   📚 第1阶段:30 | 第2阶段:40 | 第3阶段:30 | 总计:100指令")
        print("=" * 75)
        
        # 显示本次会话进度
        if self.session_stats['total'] > 0:
            rate = self.session_stats['correct']/self.session_stats['total']*100
            print(f"📊 本次练习: {self.session_stats['correct']}/{self.session_stats['total']} 正确 ({rate:.1f}%)")
            
            # 显示连胜标记
            if rate == 100:
                print("🔥 完美连胜！")
        print()
    
    def get_scenario(self, cmd):
        """为高级指令生成真实场景"""
        scenarios = {
            # 宏相关
            'q[a-z]': ('🎬 场景：你需要重复执行相同的编辑操作10次', '开始录制宏到寄存器（如qa）'),
            '@[a-z]': ('🎬 场景：刚才录制的宏需要在多处执行', '执行寄存器中的宏（如@a）'),
            
            # 可视块
            'Ctrl+v': ('📐 场景：需要在多行同一列添加注释符号', '进入可视块模式（列编辑）'),
            
            # 外部命令
            ':!command': ('💻 场景：想在Vim中查看当前目录文件列表', '执行外部命令（如:!ls）'),
            ':%!sort': ('🔄 场景：需要对文件内容按字母顺序排序', '用外部sort命令过滤整个文件'),
            
            # 数字增减
            'Ctrl+a': ('🔢 场景：光标在数字5上，想变成6', '数字增加1'),
            'Ctrl+x': ('🔢 场景：光标在数字100上，想变成99', '数字减少1'),
            
            # 全局命令
            ':g/pattern/d': ('🗑️ 场景：删除所有包含TODO的行', '删除匹配模式的行'),
            ':v/pattern/d': ('✨ 场景：只保留包含ERROR的行', '删除不匹配的行（反向匹配）'),
            
            # 帮助
            ':help': ('📖 场景：忘记了某个命令的用法', '打开Vim帮助文档'),
            
            # 组合命令演示
            '组合命令': ('🎯 场景：从当前位置删除到文件末尾', '使用组合命令 dG'),
        }
        
        if cmd in scenarios:
            return scenarios[cmd]
        return ('💡 请完成以下操作', self.all_commands.get(cmd, '执行Vim命令'))
    
    def show_question(self, cmd, description):
        """显示题目"""
        scenario, action = self.get_scenario(cmd)
        print(f"\n🔹 {scenario}")
        print(f"❓ 问题：{action}")
        
        # 为组合命令提供额外提示
        if cmd == '组合命令':
            print("💡 示例：dG (删除到末尾), y$ (复制到行尾), cw (删除单词并插入)")
        elif cmd == '[count]':
            print("💡 示例：3dd (删除3行), 5yy (复制5行), 2dw (删除2个单词)")
        
        print("-" * 75)
        print("💡 输入指令（hint=提示, skip=跳过, quit=退出）")
        print("👉 ", end="")
    
    def normalize_answer(self, answer):
        """标准化用户输入"""
        answer = answer.strip().lower()
        
        # 特殊键映射
        special_map = {
            'esc': 'Esc', '<esc>': 'Esc',
            'ctrl+r': 'Ctrl+r', 'ctrl-r': 'Ctrl+r',
            'ctrl+u': 'Ctrl+u', 'ctrl-u': 'Ctrl+u',
            'ctrl+d': 'Ctrl+d', 'ctrl-d': 'Ctrl+d',
            'ctrl+f': 'Ctrl+f', 'ctrl-f': 'Ctrl+f',
            'ctrl+b': 'Ctrl+b', 'ctrl-b': 'Ctrl+b',
            'ctrl+v': 'Ctrl+v', 'ctrl-v': 'Ctrl+v',
            'ctrl+w w': 'Ctrl+w w',
            'ctrl+w h': 'Ctrl+w h', 'ctrl+w j': 'Ctrl+w j',
            'ctrl+w k': 'Ctrl+w k', 'ctrl+w l': 'Ctrl+w l',
            'ctrl+g': 'Ctrl+g', 'ctrl-g': 'Ctrl+g',
            'ctrl+o': 'Ctrl+o', 'ctrl-o': 'Ctrl+o',
            'ctrl+i': 'Ctrl+i', 'ctrl-i': 'Ctrl+i',
            'ctrl+a': 'Ctrl+a', 'ctrl-a': 'Ctrl+a',
            'ctrl+x': 'Ctrl+x', 'ctrl-x': 'Ctrl+x',
            'zz': 'ZZ', 'wq': ':wq',
        }
        
        if answer in special_map:
            return special_map[answer]
        
        # 处理 nG 格式
        if answer.endswith('g') and answer[:-1].isdigit():
            return 'nG'
        
        # 处理宏格式
        if answer.startswith('q') and len(answer) == 2 and answer[1].isalpha():
            return 'q[a-z]'
        if answer.startswith('@') and len(answer) == 2 and answer[1].isalpha():
            return '@[a-z]'
        
        # 处理寄存器
        if answer in ['"*y', '"*yy', '"*p']:
            return '"*y' if 'y' in answer else '"*p'
        
        return answer
    
    def check_answer(self, cmd, user_answer):
        """检查答案（支持多种正确形式）"""
        normalized = self.normalize_answer(user_answer)
        
        # 精确匹配
        if normalized == cmd.lower():
            return True
        
        # 别名映射
        aliases = {
            ':wq': ['wq', ':wq!'],
            'ZZ': ['zz'],
            ':q!': ['q!'],
            'D': ['d$'], 'C': ['c$'], 'S': ['cc'],
            ':bn': [':bnext'], ':bp': [':bprev'],
            ':e!': [':edit!'],
            '组合命令': ['dG', 'y$', 'd0', 'd$', 'dw', 'cw', 'dd', 'yy'],
            '[count]': ['3dd', '5yy', '2dw', '4x', '3p', '2J'],
            ':reg': [':register', ':registers'],
            ':normal': [':norm'],
            ':g/pattern/d': [':g/pattern/delete', ':g/d'],
            ':v/pattern/d': [':v/pattern/delete', ':g!/pattern/d'],
        }
        
        if cmd in aliases and normalized in [a.lower() for a in aliases[cmd]]:
            return True
        
        # 特殊处理：用户可能输入具体的宏命令
        if cmd == 'q[a-z]' and normalized.startswith('q') and len(normalized) == 2:
            return True
        if cmd == '@[a-z]' and normalized.startswith('@') and len(normalized) == 2:
            return True
        
        return False
    
    def get_hint(self, cmd):
        """提供更好的提示"""
        hints = {
            'q[a-z]': '例如：qa 开始录制到寄存器a',
            '@[a-z]': '例如：@a 执行寄存器a中的宏',
            ':reg': '输入 :reg 查看所有寄存器',
            '"*y': '在普通模式下输入 "*y 复制到系统剪贴板',
            'Ctrl+v': '按 Ctrl+v 进入可视块模式（Windows用 Ctrl+q）',
            'R': '按大写 R 进入替换模式',
            '[count]': '在命令前加数字，如 3dd 删除3行',
            '组合命令': '将移动命令和操作命令组合，如 dG (删除到末尾)',
            ':%!sort': '输入 :%!sort 对整个文件排序',
            'gf': '光标放在文件路径上按 gf',
            'gU': '例如 gUw 将当前单词转大写',
            'zf': '例如 zf% 折叠括号内的内容',
            'Ctrl+a': '在数字上按 Ctrl+a 增加',
            'g;': '按 g; 跳转到上一个修改位置',
            ':normal': '例如 :normal i// 在每行行首添加 //',
            ':help': '输入 :help 或 :help 命令名',
        }
        return hints.get(cmd, f'试试输入: {cmd}')
    
    def get_master_tip(self, cmd):
        """显示大师技巧"""
        tips = {
            '@[a-z]': '💎 大师技巧：@@ 可以重复上一次执行的宏！',
            'Ctrl+v': '💎 大师技巧：在可视块模式按 I 或 A 可以在多行同时插入文本！',
            'q[a-z]': '💎 大师技巧：可以录制宏到寄存器 "q" 然后执行 100@q 重复100次！',
            ':g/pattern/d': '💎 大师技巧：:g 命令非常强大，可以配合 :normal 批量操作！',
            'Ctrl+a': '💎 大师技巧：配合可视块模式，可以批量递增数字！',
            ':help': '💎 大师技巧：:help 后跟命令名，如 :help w，查看具体帮助！',
        }
        return tips.get(cmd, '🎯 继续练习，成为Vim大师！')
    
    def run_practice(self, command_list, stage_name, num_questions=15):
        """运行练习核心循环"""
        if not command_list:
            print("❌ 没有可练习的指令")
            return False
        
        # 智能选题（优先错误率高的）
        questions = []
        for _ in range(num_questions):
            weights = []
            for cmd in command_list:
                stat = self.stats[cmd]
                total = stat['correct'] + stat['wrong']
                if total == 0:
                    weight = 2.0
                else:
                    wrong_rate = stat['wrong'] / total
                    weight = 1.0 + wrong_rate * 3
                weights.append(weight)
            
            selected = random.choices(command_list, weights=weights, k=1)[0]
            questions.append(selected)
        
        for idx, cmd in enumerate(questions, 1):
            self.session_stats['total'] += 1
            
            while True:
                self.print_header(stage_name)
                print(f"📝 第 {idx}/{num_questions} 题\n")
                self.show_question(cmd, self.all_commands.get(cmd, ''))
                
                user_input = input().strip()
                
                if user_input.lower() == 'quit':
                    print("\n💾 保存进度...")
                    self.save_stats()
                    return False
                elif user_input.lower() == 'hint':
                    print(f"\n💡 提示: {self.get_hint(cmd)}")
                    self.stats[cmd]['hint_used'] += 1
                    input("\n按回车键继续...")
                    continue
                elif user_input.lower() == 'skip':
                    print(f"\n⏭️ 跳过，答案: {cmd}")
                    self.stats[cmd]['wrong'] += 1
                    input("\n按回车键继续...")
                    break
                
                if self.check_answer(cmd, user_input):
                    print(f"\n✅ 正确！{self.get_master_tip(cmd)}")
                    self.stats[cmd]['correct'] += 1
                    self.session_stats['correct'] += 1
                    self.stats[cmd]['last_practiced'] = datetime.now().isoformat()
                    input("\n按回车键继续...")
                    break
                else:
                    print(f"\n❌ 错误！正确答案是: {cmd}")
                    print(f"💡 说明: {self.all_commands.get(cmd, '')}")
                    self.stats[cmd]['wrong'] += 1
                    retry = input("\n是否重试？(y/n): ").lower()
                    if retry != 'y':
                        break
        
        self.save_stats()
        return True
    
    def show_master_report(self):
        """显示大师进度报告"""
        self.print_header("大师进度报告")
        
        # 计算各阶段统计
        stages = [
            ("第一阶段：基础生存", self.stage1_list, "🔰"),
            ("第二阶段：日常提效", self.stage2_list, "⚡"),
            ("第三阶段：高阶自动化", self.stage3_list, "🚀"),
        ]
        
        total_mastered = 0
        total_commands = 0
        
        for stage_name, cmd_list, icon in stages:
            total = len(cmd_list)
            practiced = sum(1 for cmd in cmd_list if self.stats[cmd]['correct'] > 0)
            mastered = sum(1 for cmd in cmd_list if self.stats[cmd]['correct'] >= 3)
            accuracy = sum(self.stats[cmd]['correct'] for cmd in cmd_list)
            attempts = sum(self.stats[cmd]['correct'] + self.stats[cmd]['wrong'] for cmd in cmd_list)
            acc_rate = (accuracy / attempts * 100) if attempts > 0 else 0
            
            print(f"\n{icon} {stage_name}:")
            print(f"   ├─ 已接触: {practiced}/{total} ({practiced/total*100:.1f}%)")
            print(f"   ├─ 已掌握(≥3次): {mastered}/{total}")
            print(f"   └─ 正确率: {acc_rate:.1f}% ({accuracy}/{attempts})")
            
            total_mastered += mastered
            total_commands += total
        
        # 显示大师成就
        mastery_percent = total_mastered / total_commands * 100
        print(f"\n{'='*75}")
        print(f"🏆 总体掌握度: {total_mastered}/{total_commands} ({mastery_percent:.1f}%)")
        
        if mastery_percent >= 90:
            print("👑 恭喜！你已经达到 Vim 大师级别！")
        elif mastery_percent >= 70:
            print("🎉 非常优秀！再练习一下高阶技巧就能成为大师！")
        elif mastery_percent >= 50:
            print("👍 不错！继续练习，重点攻克高级功能！")
        else:
            print("💪 加油！坚持练习，Vim会大大提升你的效率！")
        
        # 显示最需要练习的5个指令
        weak_commands = []
        for cmd in self.all_commands:
            stat = self.stats[cmd]
            total = stat['correct'] + stat['wrong']
            if total >= 2 and stat['wrong'] >= stat['correct']:
                weak_commands.append((cmd, stat['wrong']/(total), stat['wrong']))
        
        if weak_commands:
            print(f"\n⚠️  需要加强的指令（错误率最高）:")
            for cmd, rate, wrong_count in sorted(weak_commands, key=lambda x: -x[1])[:5]:
                print(f"   ❌ {cmd:15s} - 错误{int(rate*100)}% ({wrong_count}次错误)")
        
        # 显示从未练习的指令
        never_practiced = [cmd for cmd in self.all_commands 
                          if self.stats[cmd]['correct'] + self.stats[cmd]['wrong'] == 0]
        if never_practiced and len(never_practiced) <= 10:
            print(f"\n📝 尚未练习的指令 ({len(never_practiced)}个):")
            print(f"   {', '.join(never_practiced[:10])}")
        
        print("\n" + "="*75)
        input("\n按回车键继续...")
    
    def master_challenge(self):
        """大师挑战：随机100题检验综合能力"""
        print("\n🔥 大师挑战模式：将随机抽取50个指令综合测试")
        print("💪 目标：正确率达到80%以上")
        input("\n按回车键开始挑战...")
        
        # 随机抽取50个指令
        all_cmds = self.stage1_list + self.stage2_list + self.stage3_list
        challenge_cmds = random.sample(all_cmds, min(50, len(all_cmds)))
        
        correct = 0
        for idx, cmd in enumerate(challenge_cmds, 1):
            print(f"\n{'='*75}")
            print(f"第 {idx}/50 题")
            scenario, action = self.get_scenario(cmd)
            print(f"🔹 {scenario}")
            print(f"❓ {action}")
            print("-" * 75)
            
            user_input = input("👉 你的答案: ").strip()
            
            if self.check_answer(cmd, user_input):
                print("✅ 正确！")
                correct += 1
                self.stats[cmd]['correct'] += 1
            else:
                print(f"❌ 错误！正确答案: {cmd}")
                print(f"📖 {self.all_commands.get(cmd, '')}")
                self.stats[cmd]['wrong'] += 1
            
            input("\n按回车键继续...")
        
        # 挑战结果
        rate = correct / 50 * 100
        print("\n" + "="*75)
        print(f"🎯 挑战完成！得分: {correct}/50 ({rate:.1f}%)")
        
        if rate >= 80:
            print("🏆 恭喜通过大师挑战！你已经掌握了Vim的核心指令！")
        elif rate >= 60:
            print("👍 不错，再练习一下高阶指令就能成为大师了！")
        else:
            print("💪 继续练习，Vim大师之路需要持之以恒！")
        
        self.save_stats()
        input("\n按回车键继续...")
    
    def main_menu(self):
        """主菜单"""
        while True:
            os.system('clear' if os.name == 'posix' else 'cls')
            print("=" * 75)
            print("   🏆 Vim 大师训练营 - 三阶段完整版 (1-100)")
            print("=" * 75)
            print("\n📚 选择练习阶段：")
            print("  1️⃣  第一阶段：基础生存 (30指令)")
            print("  2️⃣  第二阶段：日常提效 (40指令)")
            print("  3️⃣  第三阶段：高阶自动化 (30指令)")
            print("  4️⃣  综合练习 (全部100指令)")
            print("  5️⃣  薄弱点强化 (智能选题)")
            
            print("\n🎯 特殊模式：")
            print("  6️⃣  大师挑战 (50题综合测验)")
            print("  7️⃣  查看大师进度报告")
            
            print("\n⚙️  快速练习：")
            print("  8️⃣  快速10题 | 9️⃣ 标准20题 | 0️⃣ 完整35题")
            
            print("\n  q. 退出")
            
            choice = input("\n👉 请输入选项: ").strip()
            
            if choice == '1':
                self.run_practice(self.stage1_list, "第一阶段：基础生存", 15)
            elif choice == '2':
                self.run_practice(self.stage2_list, "第二阶段：日常提效", 15)
            elif choice == '3':
                self.run_practice(self.stage3_list, "第三阶段：高阶自动化", 15)
            elif choice == '4':
                all_cmds = self.stage1_list + self.stage2_list + self.stage3_list
                self.run_practice(all_cmds, "综合练习（100指令）", 20)
            elif choice == '5':
                weak = [cmd for cmd in self.all_commands 
                       if self.stats[cmd]['wrong'] > self.stats[cmd]['correct']]
                if not weak:
                    print("\n✨ 太棒了！所有指令都已掌握！")
                    input("按回车键...")
                    weak = self.stage1_list + self.stage2_list + self.stage3_list
                self.run_practice(weak, "薄弱点强化", 10)
            elif choice == '6':
                self.master_challenge()
            elif choice == '7':
                self.show_master_report()
            elif choice == '8':
                all_cmds = self.stage1_list + self.stage2_list + self.stage3_list
                self.run_practice(all_cmds, "快速10题", 10)
            elif choice == '9':
                all_cmds = self.stage1_list + self.stage2_list + self.stage3_list
                self.run_practice(all_cmds, "标准20题", 20)
            elif choice == '0':
                all_cmds = self.stage1_list + self.stage2_list + self.stage3_list
                self.run_practice(all_cmds, "完整35题", 35)
            elif choice.lower() == 'q':
                print("\n👋 恭喜完成三阶段学习！")
                print("💡 记住：:help 永远是你最好的朋友")
                print("🎉 继续保持练习，成为真正的Vim大师！")
                self.save_stats()
                sys.exit(0)
            else:
                print("\n❌ 无效选项")
                input("按回车键重试...")

def main():
    print("🚀 正在启动 Vim 大师训练营...")
    print("📚 涵盖 100 个核心 Vim 指令")
    print("💾 进度会自动保存")
    input("\n按回车键开始...")
    
    master = VimGrandMaster()
    master.main_menu()

if __name__ == "__main__":
    main()
```

---

## 🎮 使用方法

```bash
# 1. 保存代码为 vim_grandmaster.py
# 2. 运行
python3 vim_grandmaster.py

# 进度自动保存到 vim_grandmaster_stats.json
```
