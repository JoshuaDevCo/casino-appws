# Database Structure

+ Users: Lists all users who signed up, including the house itself
    + username: Uniquely identifies the user
    + email: Employed on sign in, is unique
    + password: Employed on sign in
    + money: Total money purchased by the user in the casino casino, including losses
    + currentMoney: Money currently owned by the user
    + isAdmin: Whether the user is the house or not

+ PurchaseLog: Lists all purchases by all users
    + id: Uniquely id's purchase
    + username: Identifies user
    + amount: (of money, purchased)
    + time: Date and time of purchase

+ Bets: Lists all current and past bets made in all games
    + id: Uniquely id's bet
    + username: Identifies user
    + amount: (of money, betted)
    + game: In which game is it betted (currently can only be roulette)
    + position: A string in a game-dependent format identifying what is being betted on\
        > For roulette it is the names of all layout cells affected (and including "enPrison" if the bet is in said state) joined by "&"s, then "|" and then binary numbers indicating the settings (whether it is a french roulette, is _la partage_ enabled, is _en prison_ enabled, resp.)
    + fate: If it was moved, the id of the new bet, other faiths use attribute winner
    + winner: Username of winner, null if the bet was moved
    + previous: If it is a moved bet, the id of the previous bet, null if the bet is original
    + betTime: Date and time of bet creation (or of move if it's a moved bet)
    + deathTime: Date and time when the bet was won/lost/moved
