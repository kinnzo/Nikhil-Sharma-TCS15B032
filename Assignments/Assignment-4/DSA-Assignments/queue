--This is a program to implement Queue in Elm

import Html exposing (Html, Attribute, button, div, input, text)
import Html.Attributes exposing (..)
import Html.Events exposing (..)
import String


main =

  Html.beginnerProgram { model = model, view = view, update = update }


-- MODEL

type alias Model =
  {
  content : String,
  operation : String
  }

model : Model
model =
  { content = "",  operation="" }


-- UPDATE

type Msg
  = Change1 String | Change2 String | Pop

update : Msg -> Model -> Model
update msg model =
  case msg of
    Change1 newContent ->
      { model | content = newContent}
    Change2 newContent ->
      { model | content = model.content ++ String.right 1 newContent}
    Pop ->
      { model | content = String.dropLeft 1 model.content}
-- VIEW

view : Model -> Html Msg
view model =
  div []
    [ input [ placeholder "The list", onInput Change1] []
    , div [] [ text (toString (String.toList model.content))]
    , input [placeholder "Number to Push",  onInput Change2 ] []
    , button [ onClick Pop ] [ text "PoP" ]
    ]
