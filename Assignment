#include <iostream>

int main(){
	int i, n, time, rem;
	int  temp = 0, qt;
	float wt = 0, tat = 0;
	std::cout << "Enter the total number of processes : ";
	std::cin >> n;
	rem = n;
	
	int at[n];
	int bt[n];
	int rt[n];
	
	for (i = 0; i < n; i++) {
		std::cout << "Arrival time for process " << i << ": ";
		std::cin >> at[i];
		std::cout << "Burst time for process " << i << ": ";
		std::cin >> bt[i];
		rt[i] = bt[i];
	}

	std::cout << "Enter quantum time: ";
	std::cin >> qt;
	
	int process_schedule[1000] = {0}; 
	std::cout << "\nGantt chart:\n";
	std::cout << "-----------\n";
	
	std::cout << "0";
	for (time = 0; rem != 0;) {
		if (rt[i] <= qt && rt[i] > 0) {
			time += rt[i];
			rt[i] = 0;
			temp = 1;
		}
		else if (rt[i] > 0) {
			rt[i] -= qt;
			time += qt;
		}

		if (rt[i] == 0 && temp == 1) {
			rem--;
			std::cout << "-> [P" << i << "] <- " << time;
			process_schedule[time] = i+1; 
			tat += time - at[i];
			wt += tat - bt[i];
			temp = 0;
		}

		if (i == n-1) {
			i = 0;
		}
		else if (at[i+1] <= time) {
			i++;
		}
		else {
			i = 0;
		}
	}
	
	
	std::cout << "\n\nProcess schedule:"<<std::endl;
	std::cout << "\n-----------------\n";
	for (i = 0; i < time; i++) {
		if (process_schedule[i] != 0) {
			std::cout << "P" << process_schedule[i]-1 << "  ";
		}
		else {
			std::cout << "-  ";
		}
	}
	
	std::cout << "\n\nAvg waiting time: " << wt/n << std::endl;
	std::cout << "Avg turnaround time: " << tat/n << std::endl;
	
}
