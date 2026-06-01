# Script123main.lua
idk bro
-- Ein Skript in Roblox Studio, um Code von GitHub zu laden
local HttpService = game:GetService("HttpService")

-- Ersetze diesen Link mit deinem kopierten "Raw"-Link von GitHub
local githubUrl = "https://raw.githubusercontent.com/DEIN_BENUTZERNAME/DEIN_REPOSITORY/main/movement.lua"

local success, result = pcall(function()
	return HttpService:GetAsync(githubUrl)
end)

if success then
	-- loadstring führt den heruntergeladenen Text als ausführbaren Code aus
	local chunk, err = loadstring(result)
	if chunk then
		print("Skript erfolgreich von GitHub geladen!")
		chunk() -- Führt das geladene Skript aus
	else
		warn("Fehler beim Kompilieren des Skripts: " .. tostring(err))
	end
else
	warn("Fehler beim Abrufen der Datei von GitHub: " .. tostring(result))
end
