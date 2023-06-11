% Required month and day information for calculating the number of days
days_in_month(1, 31).
days_in_month(2, 28).
days_in_month(3, 31).
days_in_month(4, 30).
days_in_month(5, 31).
days_in_month(6, 30).
days_in_month(7, 31).
days_in_month(8, 31).
days_in_month(9, 30).
days_in_month(10, 31).
days_in_month(11, 30).
days_in_month(12, 31).

% Rule to calculate the number of days between two dates 
days_between_dates(Date1, Date2, Days) :-
    Date1 = date(2023, Month1, Day1),
    Date2 = date(2023, Month2, Day2),
    calculate_days(Month1, Day1, Month2, Day2, Days).


% Auxiliary rule to calculate the number of days between two dates 
% Base case: If the two dates are the same, return 0
calculate_days(Month, Day, Month, Day, 0).

% Recursive case 1: If the starting month is less than the ending month
calculate_days(Month1, Day1, Month2, Day2, Days) :-
    Month1 < Month2,
    days_in_month(Month1, DaysInMonth), % Get the number of days in the current month
    RemainingDays is DaysInMonth - Day1, % Calculate the remaining days in the current month
    NextMonth is Month1 + 1, % Move to the next month
    calculate_days(NextMonth, 0, Month2, Day2, RemainingDaysInNextMonth), % Recursive call for the next month
    Days is RemainingDays + RemainingDaysInNextMonth. % Calculate the total days

% Recursive case 2: If the starting month is the same as the ending month
calculate_days(Month1, Day1, Month2, Day2, Days) :-
    Month1 =:= Month2,
    Days is Day2 - Day1. % Calculate the difference in days within the same month

