# laba1_ICS
% Дневная смена
change(mary, day).
change(sue, day).
change(jane, day).

% Вечерняя смена
change(sam, evening).
change(jane, evening).
change(bob, evening).
change(patricia, evening).

% Знают ли друг друга A и B
knows(A, B) :- change(A, Shift), change(B, Shift).

% Кто работает в дневную смену
day_shift_workers(Worker) :- works(Worker, day).

% Есть ли кто-то, кто работает в обе смены
works_both_shifts(Worker) :- works(Worker, day), works(Worker, evening).

% Есть ли кто-то, кто не знает друг друга
does_not_know(A, B) :- change(A, ShiftA), change(B, ShiftB), ShiftA = ShiftB.
