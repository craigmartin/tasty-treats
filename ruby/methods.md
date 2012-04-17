# Tricks with Methods

## open? method

expressions: opens_at and closes_at

<pre><code>def open?
  Time.now.between? opens_at, closes_at
end
</code></pre>

kudos = Dan Croak (Robots Smashing)
