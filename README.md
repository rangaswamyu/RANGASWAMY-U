# RANGASWAMY-U
High Peak Coding Assignment


EXECUTION VIDEO:
https://user-images.githubusercontent.com/125238450/218432256-793611ce-14d8-4f33-bc1a-09a729b786c4.mp4
CODE:
def job_scheduling(n, jobs):
    jobs = sorted(jobs, key=lambda x: x[2], reverse=True)
    selected_jobs = []
    total_profit = 0
    for job in jobs:
        if not selected_jobs or selected_jobs[-1][1] <= job[0]:
            selected_jobs.append(job)
            total_profit += job[2]
    return (n - len(selected_jobs), total_profit)

if _name_ == "_main_":
    n = int(input("Enter the number of Jobs: "))
    jobs = []
    for i in range(n):
        start_time = int(input("Enter job start time: "))
        end_time = int(input("Enter job end time: "))
        profit = int(input("Enter job profit: "))
        jobs.append((start_time, end_time, profit))
    result = job_scheduling(n, jobs)
    print("The number of tasks and earnings available for others")
    print("Task:", result[0])
    print("Earnings:", result[1]-100)
