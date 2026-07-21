# 1. สร้างโฟลเดอร์โปรเจกต์และย้ายเข้าไป
mkdir ai-knowledge-base
cd ai-knowledge-base

# 2. สร้างโฟลเดอร์ย่อย knowledge
mkdir knowledge

# 3. สร้างไฟล์ README.md
cat << 'EOF' > README.md
# AI Knowledge Base & Developer Guidelines

คลังความรู้ คลังโค้ดตัวอย่าง และกฎการเขียนโค้ดสำหรับนำไปใช้เป็นบริบท (Context / Knowledge Base) ให้กับ AI Assistants

---

## 📁 โครงสร้างคลังความรู้ (Repository Structure)

| ไฟล์ / โฟลเดอร์ | รายละเอียดความรู้ |
| :--- | :--- |
| `RULES.md` | กฎระเบียบ ข้อบังคับ และ Coding Standards ที่ AI ต้องปฏิบัติตามอย่างเคร่งครัด |
| `knowledge/01_combat_system.md` | โครงสร้างและ Logic ของระบบต่อสู้ (Combo M1-M4, Hitbox, State Management) |
| `knowledge/02_ui_design_system.md` | แนวทางและ Pattern การสร้าง UI สไตล์ Dark Minimalist |
| `knowledge/03_script_security.md` | ระบบความปลอดภัย Key Verification System และ Discord Webhook Integration |
| `knowledge/04_discord_bot.md` | โครงสร้าง Python Discord Bot สำหรับ Scraping & Audio Asset Tracking |
EOF

# 4. สร้างไฟล์ RULES.md
cat << 'EOF' > RULES.md
# Developer & AI Coding Rules

เอกสารกำหนดสเปกและกฎระเบียบสำหรับการเขียนโค้ด ให้ AI อ่านและปฏิบัติตาม **อย่างเคร่งครัด**

---

## 🎯 กฎเหล็กประจำโปรเจกต์ (Core Constraints)

1. **Strict Code Preservation:**
   * ห้ามลบ รื้อ หรือเปลี่ยนแปลงโครงสร้างเดิมของโค้ดที่มีอยู่แล้วโดยไม่จำเป็น
   * ให้ใช้วิธี **"เขียนต่อเติม" (Extend)** หรือ **"ปรับแก้เฉพาะจุดที่กำหนด" (Patch)** เท่านั้น

2. **Naming Conventions:**
   * **Lua / Luau:** ใช้ `PascalCase` สำหรับ Class, Module, Service และ Function Name (เช่น `ComboService`, `CreateHitbox`)
   * **Variables:** ใช้ `camelCase` หรือ `PascalCase` อย่างสอดคล้อง
   * **Python:** ใช้ `snake_case` สำหรับตัวแปรและฟังก์ชัน, `PascalCase` สำหรับ Class

3. **Architecture Style:**
   * **Lua/Luau:** ให้ใช้รูปแบบ **Object-Oriented Programming (OOP)** ด้วย `Metatable` สำหรับระบบที่เป็น Module
   * **UI Style:** ยึดดีไซน์แบบ **Modern Minimalist (Dark Theme)** พร้อม Neon Accents (เน้นโทนสีเข้ม เช่น Charcoal, Obsidian)
   * **Network & Security:** แยก Logic ระหว่าง Client และ Server อย่างเด็ดขาด (Server-side Validation เสมอ)

4. **Response Format:**
   * ให้คำอธิบายภาษาไทยแบบกระชับ ตรงประเด็น
   * แสดงโค้ดสมบูรณ์ ปราศจากบล็อกว่าง (No placeholder / incomplete code)
EOF

# 5. สร้างไฟล์ความรู้ในโฟลเดอร์ knowledge/
cat << 'EOF' > knowledge/01_combat_system.md
# Knowledge Base: Combat System & Combo Logic

## Standard Module Pattern (Luau OOP)

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
