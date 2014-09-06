#!usr/bin/env python
'''
Homework of the first week for the Algorithm Thinking 
takes a file with the data of relationship of article citation, convert to directed 
graph dictionary, and plot the distribution.
'''
from graph_compute import in_degree_distribution
from matplotlib import pyplot

def load_graph(file_name):
    '''
    Function that load a graph given the file,
    returns a dictionary that models a graph
    '''
    graph_file = open(file_name, 'r', -1)
    graph_text = graph_file.read()
    graph_lines = graph_text.split('\n')
    graph_file.close()
    
    answer_graph = dict([])
    for line in graph_lines:
        neighbors = line.split(' ')
        #print line
        node = int(neighbors[0])
        answer_graph[node] = set([])
        for neighbor in neighbors[1:-1]:
            #there is a space in the end
            answer_graph[node].add(int(neighbor))
    return answer_graph
    
def normalize_distri(digraph):
    '''
    Take a directed graph file, return the normalized in-degree distribution'
    '''
    distribution = in_degree_distribution(digraph)
    nor_distri = dict([])
    values_sum = sum(distribution.values())
    for node,value in distribution.items():
        nor_distri[node] = float(value) / float(values_sum)
    return nor_distri
    

if __name__ == '__main__':
    '''
    plot the normalized distribution
    '''
    nor_distri = normalize_distri((load_graph('data-cite.txt')))
    nor_distri.pop(0, None)
    keys = nor_distri.keys()
    values = nor_distri.values()
    pyplot.loglog(keys, values, 'o')
    pyplot.title('Citation Distribution')
    pyplot.xlabel('Number of Cited Article')
    pyplot.ylabel('Distribution')
    pyplot.show()
      


            
