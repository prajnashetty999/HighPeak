# HighPeak

#Problem Statements - Goodie Dilemma

#Tech Stacks
*Python
*Vscode

#Code

from collections import namedtuple
Job = namedtuple('Job', ['start', 'end', 'profit'])
def maximize_earnings(jobs):
  # sort the jobs by decreasing profit
  jobs.sort(key=lambda x: -x.profit)
  selected_jobs = []
  earnings = 0
  # iterate through the jobs and select the non-overlapping ones
  for job in jobs:
    if all(job.start >= selected_job.end or job.end <= selected_job.start for selected_job in selected_jobs):
      selected_jobs.append(job)
      earnings += job.profit
  # calculate the remaining number of jobs and earnings
  remaining_jobs = len(jobs) - len(selected_jobs)
  remaining_earnings = sum(job.profit for job in jobs) - earnings
  return remaining_jobs, remaining_earnings
# prompt the user to input the list of jobs
jobs = []
num_of_jobs=int(input("Enter the number of Jobs\n"))
print('Enter job start time, end time, and earnings')
for _ in range(num_of_jobs):
  start = input()
  end = input()
  profit = input()
  jobs.append(Job(start=int(start), end=int(end), profit=int(profit)))
remaining_jobs, remaining_earnings = maximize_earnings(jobs)
print('The number of tasks and earnings available for others')
print(f"Task: {remaining_jobs}")
print(f"Earnings: {remaining_earnings}")






https://user-images.githubusercontent.com/106021656/210538484-bb7aa3a9-70ca-4508-abdd-9daf624eddb1.mp4

