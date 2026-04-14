vector<int> visited(edges.size() + 2,0);

        for (int i = 0; i < edges.size(); i++) {
            visited[edges[i][0]]++;
            visited[edges[i][1]]++;
        }

        int max = INT_MIN;
        int index;

        for (int i = 0; i < visited.size(); i++) {
            if (max < visited[i]) {
                max = visited[i];
                index = i;
            }
        }

        return index;