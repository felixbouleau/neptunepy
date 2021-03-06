Data colleciton and API usage for Neptune's Pride 2

STATUS: IN DEVELOPMENT (Python 3.3.2)

Example USAGE:

import neptunepy.neptune as npt
def main():
	# Get Neptune instance
	neptune = npt.Neptune()

	# Connect to your online account
	neptune.connect(<username>, <password>)

	# List games that you have
	games = neptune.listGames()

	# Once you have connected, you can choose which game 
	# to reference by setting the game number. The game number
	# For example if you only had one game, you could use
	# neptune.open_games[0]["number"]
	neptune.setGameNumber(neptune.open_games[<gameindex>]["number"])

	# Now you can load game data either from the game directly
	# or from the stashed data hosted by a private server running
	# neptunepy to collect game data. To get game data directly from
	# neptune server call fetchLiveReport().
	neptune.fetchLiveReport()

	# Anytime you fetch data is populates a report object
	# which you can access directly, or through the report_history
	# dictionary where the key is the tick number you want
	latest_report = neptune.report
	tick100 = neptune.report_history[100]

	# A report consists of the following:
	+ fleet_speed
	+ paused
	+ productions
	+ tick_fragment
	+ now
	+ tick_rate
	+ production_rate
	+ stars_for_victory
	+ game_over
	+ started
	+ start_time
	+ total_stars
	+ production_counter
	+ trade_scanned
	+ tick
	+ trade_cost
	+ name
	+ player_uid
	+ admin
	+ turn_based
	+ war
	+ turn_based_time_out
	+ stars
	    - uid
		- owner
		- name
		- visible
		- position
		+ if visible == True
		    - economy
			- science
			- industry
			- garrison
			- naturalResources
			- totalResources
			- shipCount
	+ fleets
		- uid
	+ players
		- uid