# assignment2-Ravipati

# Navya Ravipati
###### The National Gallery
The National Gallery is an **art museum** in Trafalgar Square in the City of Westminster, in Central London, England. Founded in 1824, it houses a **collection of over 2,300 paintings** dating from the mid-13th century to 1900.
---

# ordered list of museum
 London Heathrow (LHR) airport
 1. We recommend flying to London Heathrow (LHR) Airport
 2. which is 14.4 miles away from London. The train and subway from London Heathrow (LHR) to London takes 31 min.
 3. stay i.e, There are 2000+ hotels available in National Gallery. Prices start at $100 USD per night.

 # unordered list 
 * Smithsonian National Museum of Natural History.
 * National Museum of African American History and Culture.
    * U.S. Capitol.
    * Lincoln Memorial.
 * National Gallery of Art.
 * United States Holocaust Memorial Museum.
 * Library of Congress.
 * National Air and Space Museum.

 Link to [click here to know in detail AboutMe](AboutMe.md)

---
# INTERESTING PLACES TO VISIT IN CITIES

Some of the cities i would like to recommend to visit the locations people like most. 


|CITY|LOCATION|TIME|
|----|--------|----|
|USA|LAS VEGAS|3 HOURS|
|INDIA|DELHI|4 HOURS|
|AUSTRALIA|SYDNEY|6 HOURS|
|UK|LONDON|8 HOURS|


---
# IMPORTANT QUOTES

> In a conflict between the heart and the brain, follow your heart.
*Swami Vivekananda*

> The greatest sin is to think yourself weak.
*Swami Vivekananda*


---
# CODE SNIPPET

> Closing Tag Is Being Outputted To Early In A While Loop - PHP

[LINK TO STACK OVERFLOW](https://stackoverflow.com/questions/73642710closing-div-tag-is-being-outputted-to-early-in-a-while-loop-php)


```
<div class="column">
    <?php

        $s = "SELECT boards.board_name, boards.board_id, images.filename
        FROM boards
        INNER JOIN boards_images ON boards_images.board_id = boards.board_id
        INNER JOIN images        ON boards_images.image_id = images.image_id
        WHERE boards.user_id = :user_id";

        $stmt = $connection->prepare($s);
        $stmt -> execute([
            ':user_id' => $db_id  // $db_id is from a $_SESSION login value
        ]);

        $dbBoardname_last = '';
        $imgcount = 0;

        while ($row = $stmt->fetch()) {

            $dbBoardname = htmlspecialchars($row['board_name']);
            $dbImageFile = "$wwwRoot/images-lib/" . htmlspecialchars($row['filename']);

            //if the board name is the same as the previous $row only add images. 
            if($dbBoardname != $dbBoardname_last) {

                //reset the image count for new boards
                $imgcount = 0;

                echo "
                <div class='board-component'>
                    <h2>{$dbBoardname}</h2>
                ";
            }

            // if less than 4 images   
            if($imgcount < 4) { 
                echo "
                <img src='{$dbImageFile}'>
                ";
            }

            $imgcount+=1;
            
            // close the board component div
            if($dbBoardname != $dbBoardname_last) {
                echo "
                </div>
                ";
            }
            //record the last board_name to check if a new board element should be created
            $dbBoardname_last = $dbBoardname;
        } 
    ?>
</div>
```
[LINK TO CODE](https://www.php.net/crypt)