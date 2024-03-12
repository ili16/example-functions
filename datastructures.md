# Python

def array_example():
    array = [1, 2, 3, 4, 5]
    return array

class Stack:
    def __init__(self):
        self.stack = []

    def push(self, item):
        self.stack.append(item)

    def pop(self):
        if not self.is_empty():
            return self.stack.pop()

    def is_empty(self):
        return len(self.stack) == 0

from collections import deque

def queue_example():
    queue = deque([1, 2, 3, 4, 5])
    return queue

def set_example():
    set_data = {1, 2, 3, 4, 5}
    return set_data

def dictionary_example():
    dictionary = {'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5}
    return dictionary

# Java

import java.util.ArrayList;
import java.util.List;

public class ArrayExample {
    public List<Integer> arrayExample() {
        List<Integer> list = new ArrayList<>();
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);
        return list;
    }
}

import java.util.Stack;

public class StackExample {
    public Stack<Integer> stackExample() {
        return new Stack<>();
    }
}

import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {
    public Queue<Integer> queueExample() {
        return new LinkedList<>();
    }
}

import java.util.HashSet;
import java.util.Set;

public class SetExample {
    public Set<Integer> setExample() {
        return new HashSet<>();
    }
}

import java.util.HashMap;
import java.util.Map;

public class MapExample {
    public Map<String, Integer> mapExample() {
        return new HashMap<>();
    }
}

// JavaScript

function fetchDataAndProcess(callback) {
    fetchData(function(data) {
        processData(data, function(result) {
            callback(result);
        });
    });
}

function arrayExample() {
    return [1, 2, 3, 4, 5];
}

class Stack {
    constructor() {
        this.stack = [];
    }

    push(item) {
        this.stack.push(item);
    }

    pop() {
        if (!this.isEmpty()) {
            return this.stack.pop();
        }
    }

    isEmpty() {
        return this.stack.length === 0;
    }
}

function queueExample() {
    return [1, 2, 3, 4, 5];
}

function setExample() {
    return new Set([1, 2, 3, 4, 5]);
}

function mapExample() {
    return { 'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5 };
}

# C++

#include <vector>

std::vector<int> arrayExample() {
    return {1, 2, 3, 4, 5};
}

#include <stack>

std::stack<int> stackExample() {
    return std::stack<int>();
}

#include <queue>

std::queue<int> queueExample() {
    return std::queue<int>();
}

#include <unordered_set>

std::unordered_set<int> setExample() {
    return std::unordered_set<int>();
}

#include <unordered_map>

std::unordered_map<char, int> mapExample() {
    return std::unordered_map<char, int>();
}

# Ruby

def array_example
    [1, 2, 3, 4, 5]
end

class Stack
    def initialize
        @stack = []
    end

    def push(item)
        @stack.push(item)
    end

    def pop
        @stack.pop
    end

    def is_empty
        @stack.empty?
    end
end

def queue_example
    [1, 2, 3, 4, 5]
end

def set_example
    [1, 2, 3, 4, 5].to_set
end

def map_example
    { 'a' => 1, 'b' => 2, 'c' => 3, 'd' => 4, 'e' => 5 }
end


# Go

package main

func arrayExample() []int {
	return []int{1, 2, 3, 4, 5}
}

package main

type Stack struct {
	items []int
}

func (s *Stack) push(item int) {
	s.items = append(s.items, item)
}

func (s *Stack) pop() int {
	if !s.isEmpty() {
		item := s.items[len(s.items)-1]
		s.items = s.items[:len(s.items)-1]
		return item
	}
	return 0 // Or handle error appropriately
}

func (s *Stack) isEmpty() bool {
	return len(s.items) == 0
}

package main

func queueExample() []int {
	return []int{1, 2, 3, 4, 5}
}

package main

import "sort"

func setExample() []int {
	set := []int{1, 2, 3, 4, 5}
	sort.Slice(set, func(i, j int) bool {
		return set[i] < set[j]
	})
	return set
}

package main

func mapExample() map[string]int {
	return map[string]int{"a": 1, "b": 2, "c": 3, "d": 4, "e": 5}
}