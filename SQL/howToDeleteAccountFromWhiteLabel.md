DELETE FROM `accounts` WHERE id NOT IN (500, 520, 536, 527, 526, 525, 519);
DELETE FROM `account_preferences` WHERE account_id NOT IN (500, 520, 536, 527, 526, 525, 519);
DELETE FROM `contest_pools` WHERE account_id NOT IN (500, 520, 536, 527, 526, 525, 519);
DELETE FROM `contest_results` WHERE account_id NOT IN (500, 520, 536, 527, 526, 525, 519);
DELETE FROM `contest_split_payments` WHERE account_id NOT IN (500, 520, 536, 527, 526, 525, 519);
DELETE FROM `contest_winners` WHERE account_id NOT IN (500, 520, 536, 527, 526, 525, 519);
DELETE FROM `customer_information_manager` WHERE account_id NOT IN (500, 520, 536, 527, 526, 525, 519);
TRUNCATE email_sign_up;
DELETE FROM `fantasy_picks` WHERE account_number NOT IN (500, 520, 536, 527, 526, 525, 519);
DELETE FROM `game_credits` WHERE account_id NOT IN (500, 520, 536, 527, 526, 525, 519);
TRUNCATE login_attempts;
DELETE FROM `vnet_ledger` WHERE account_id NOT IN (500, 520, 536, 527, 526, 525, 519);
DELETE FROM `w9_status` WHERE account_id NOT IN (500, 520, 536, 527, 526, 525, 519);


DELETE FROM `accounts` WHERE id NOT IN (500, 66712, 66666);
DELETE FROM `account_preferences` WHERE account_id NOT IN (500, 66712, 66666);
DELETE FROM `contest_pools` WHERE account_id NOT IN (500, 66712, 66666);
DELETE FROM `contest_results` WHERE account_id NOT IN (500, 66712, 66666);
DELETE FROM `contest_split_payments` WHERE account_id NOT IN (500, 66712, 66666);
DELETE FROM `contest_winners` WHERE account_id NOT IN (500, 66712, 66666);
DELETE FROM `customer_information_manager` WHERE account_id NOT IN (500, 66712, 66666);
TRUNCATE email_sign_up;
DELETE FROM `fantasy_picks` WHERE account_number NOT IN (500, 66712, 66666);
DELETE FROM `game_credits` WHERE account_id NOT IN (500, 66712, 66666);
TRUNCATE login_attempts;
DELETE FROM `vnet_ledger` WHERE account_id NOT IN (500, 66712, 66666);
DELETE FROM `w9_status` WHERE account_id NOT IN (500, 66712, 66666);