- #+BEGIN_QUERY
  {:query [:find (pull ?b [*])
           :where [?b :block/marker ?marker]
                  [(= ?marker "TODO")]]
   :result-transform (fn [result] (sort-by :block/priority result))}
  #+END_QUERY
-