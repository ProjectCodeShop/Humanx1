# 1. อัปเดตแพ็กเกจในระบบให้เป็นเวอร์ชันล่าสุด
pkg update && pkg upgrade -y

# 2. ติดตั้ง Git, Python, Node.js และเครื่องมือสำหรับแก้ไขไฟล์
pkg install git python nodejs-lts nano curl wget -y

# เปลี่ยนข้อมูลในอัญประกาศให้เป็นของคุณ
git config --global user.name "YOUR_GITHUB_USERNAME"
git config --global user.email "YOUR_EMAIL@gmail.com"

# สร้างโฟลเดอร์โปรเจกต์และโฟลเดอร์ความรู้
mkdir -p ai-knowledge-base/knowledge && cd ai-knowledge-base

# สร้างไฟล์ README.md
cat << 'EOF' > README.md
# AI Knowledge Base & Developer Guidelines

คลังความรู้ คลังโค้ดตัวอย่าง และกฎการเขียนโค้ดสำหรับนำไปใช้เป็นบริบท (Context / Knowledge Base) ให้กับ AI Assistants

## 📁 โครงสร้างคลังความรู้
| ไฟล์ / โฟลเดอร์ | รายละเอียดความรู้ |
| :--- | :--- |
| `RULES.md` | กฎระเบียบ ข้อบังคับ และ Coding Standards |
| `knowledge/01_combat_system.md` | โครงสร้างระบบต่อสู้ (Combo M1-M4, Hitbox) |
| `knowledge/02_ui_design_system.md` | แนวทาง UI สไตล์ Dark Minimalist |
| `knowledge/03_script_security.md` | ระบบความปลอดภัย Key Verification System |
| `knowledge/04_discord_bot.md` | โครงสร้าง Python Discord Bot |
EOF

# สร้างไฟล์ RULES.md
cat << 'EOF' > RULES.md
# Developer & AI Coding Rules

1. **Strict Code Preservation:** ห้ามลบ/รื้อโค้ดเดิม ให้ใช้วิธีต่อเติม (Extend) เท่านั้น
2. **Naming Conventions:** Lua/Luau ใช้ PascalCase สำหรับ Class/Module
3. **Architecture Style:** Luau ใช้ OOP ด้วย Metatable / UI ยึด Dark Minimalist (Obsidian/Charcoal)
4. **Response Format:** แสดงโค้ดสมบูรณ์ ปราศจากบล็อกว่าง
EOF

# สร้างไฟล์ในโฟลเดอร์ knowledge/
cat << 'EOF' > knowledge/01_combat_system.md
# Knowledge Base: Combat System & Combo Logic

```lua
local CombatModule = {}
CombatModule.__index = CombatModule

function CombatModule.new(player: Player)
    local self = setmetatable({}, CombatModule)
    self.Player = player
    self.ComboStep = 1
    self.LastHitTime = 0
    self.IsAttacking = false
    self.ComboResetDelay = 1.2
    return self
end

function CombatModule:ExecuteCombo()
    local currentTime = os.clock()
    if currentTime - self.LastHitTime > self.ComboResetDelay then
        self.ComboStep = 1
    end
    if self.IsAttacking then return end
    self.IsAttacking = true
    self.LastHitTime = currentTime
    
    if self.ComboStep >= 4 then
        self.ComboStep = 1
        task.wait(2.5)
    else
        self.ComboStep += 1
        task.wait(0.3)
    end
    self.IsAttacking = false
end

return CombatModule
