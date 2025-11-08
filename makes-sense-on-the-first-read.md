Problem: ```Data = xs |> Array.map (snd >> fst) |> FieldData.fromRows``` this is very short and sweet but not readable and explicit. can you make it explicit so any programmer is able to make sense of it on the first read

>>> 
  The original was a composition of functions that, while concise, sacrificed
  readability. Sometimes it's worth being more verbose to make the code's intent
  immediately clear to other developers (or yourself in 6 months).

  Here's a more explicit and readable version:

    let extractDataFromRows xs =
        let extractSecondAndFirstElements =
          xs
          |> Array.map (fun tuple ->
            tuple
            |> snd 
            |> fst
          )

        let fieldData = FieldData.fromRows extractSecondAndFirstElements
        fieldData

  Now it's clear that we're:

  1. Taking a tuple array
  2. For each tuple, getting its second element (using  snd )
  3. From that second element (also a tuple), getting its first element
  4. Finally converting the resulting array into a FieldData structure

UPDATE: is the latter really readable? perhaps if the reader is not comfortable with the `>>` syntax. but really the first one is readable for a more experience dev because it implies first get the second element in tuple and then within that tuple get the first
