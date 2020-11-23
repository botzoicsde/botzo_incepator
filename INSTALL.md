#INSTALLATION

[RO] 

Asigura-te ca adaugi urmatoarele functii in vrp/base.lua (Daca nu exista deja)

function vRP.getUserHoursPlayed(user_id)
	if(hoursPlayed[user_id] ~= nil)then
		return math.floor(hoursPlayed[user_id])
	else
		return 0
	end
end

function tvRP.updateHoursPlayed(hours)
	user_id = vRP.getUserId(source)
  MySQL.Async.execute("UPDATE vrp_users SET hoursPlayed = hoursPlayed + @hours WHERE id = @user_id",{["hours"] = hours,["user_id"] = user_id}, function(data)end)
  hoursPlayed[user_id] = hoursPlayed[user_id] + hours
end


[EN]


Be sure to add the following functions in vrp/base.lua (If it doesn't already exist)

function vRP.getUserHoursPlayed(user_id)
	if(hoursPlayed[user_id] ~= nil)then
		return math.floor(hoursPlayed[user_id])
	else
		return 0
	end
end

function tvRP.updateHoursPlayed(hours)
	user_id = vRP.getUserId(source)
  MySQL.Async.execute("UPDATE vrp_users SET hoursPlayed = hoursPlayed + @hours WHERE id = @user_id",{["hours"] = hours,["user_id"] = user_id}, function(data)end)
  hoursPlayed[user_id] = hoursPlayed[user_id] + hours
end
