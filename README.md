# total-recall

A minimalist, limited event sourcing platform.  Analogous to a debugger working
over lines of code in a computer program.  Use step, run and steps to work
backwards or forwards in time applying events over state.

Customise your validation and success functions for stat computation.

Provisions for making events durable in an appending log file.  Plug in something
more capable like Datomic if you would like to.

Inspired by the simplicity of the Clojure programming language, and thoughts on
working with values (events as data) in The Joy of Clojure.

## Usage

    (defn validation-fn [evt] #(:some-attrib evt))

    (defn success-fn [{:keys [h] :or {h 0}} evt e-filter]
      (if (= (:some-attrib evt) e-filter) (inc h) h))

    (run {} events validation-fn success-fn :some-event-type)

## Release information

* Latest development release is 0.1.0


Enjoy!
