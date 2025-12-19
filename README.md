#!/bin/bash

pass=0
fail=0

read -p "Enter number of students: " n

for ((i=1; i<=n; i++)); do
    echo "Student $i"

    read -p "Enter Student ID: " sid
    read -p "Enter marks of subject 1: " m1
    read -p "Enter marks of subject 2: " m2
    read -p "Enter marks of subject 3: " m3

    total=$(( $m1 + $m2 + $m3 ))
    percentage=$(( $total * 100 / 300 ))

    echo "Total Marks: $total"
    echo "Percentage: $percentage%"

    if [ "$percentage" -ge 40 ]; then
        echo "Result: Pass"
        pass=$(( $pass + 1 ))
    else
        echo "Result: Fail"
        fail=$(( $fail + 1 ))
    fi

    echo "----------------------"
done

echo "Final Summary"
echo "Total Pass: $pass"
echo "Total Fail: $fail"
