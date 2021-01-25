# TheaterCMS-Project
Website Development for a Local Theater, Front-End Focused

Over a 10 day sprint with the Tech Academy, I worked with my peers in a team developing a full scale MVC/MVVM Web Application in C#. Working on an actual product for a local theater company was a great learning oppertunity for fixing bugs, cleaning up code, and adding requested features. There were some big changes that could have been a large time sink, but we used what we had to deliver what was needed on time. I saw how a good developer works with what they have to make a quality product. Much of the site had already been built, leaving a good deal of front end stories and UX improvements that needed to be completed, all of varying degrees of difficulty. Everyone on the team had a chance to work on front end and back end stories, I chose to focus on [front end stories](#front-end-stories) to better refine my skills in this area. This project taught me much more than just software development, I built project management and team programming [skills](#other-skills-learned) that I'm confident I will implement on future projects.

Below are descriptions of the stories I worked on, along with code snippets and navigation links. 

## Front-End Stories
* [Message Bar](#message-bar)
* [CopyToClip](#copytoclip)

### Message Bar

Messaging.cshtml

<div class="newMsgBar">
  <i class="newMsgCommentDotsIcon fas fa-comment-dots"></i>
  <i class="newMsgIndicator fas fa-circle fa-stack"></i>
  <span class="newMsgQuantity">&nbsp;4 </span>
  <span class="newMsgTitle">&nbsp;New Messages</span>
  <i class="newMsgUpIcon fas fa-angle-up" id="chevButton"></i>
</div>
<textarea id="chatTextArea"></textarea>


<script>
  var $chatBox = $("textarea");

  @*Chatbox to rise from the msgBar*@
  $("#chevButton").click(function () {
    if ($chatBox.css("bottom") == "-440px") {
      $("textarea").animate({
        bottom: 0
      }, "slow");
      $("#chevButton").css({ "transform": "rotate(" + 180 + "deg)" });
    }
    @*Chatbox to fall into the msgbar*@
    else {
      $("textarea").animate({
        bottom: -440
      }, "slow");
    }
  });
</script>

CSS

/*=================== Message Bar ===================*/

.newMsgBar {
    overflow: hidden;
    cursor: pointer;
    position: fixed;
    bottom: 0;
    left: 0;
    width: 325px;
    background-color: #1a1a1a;
    z-index: 5; /* Must be at least 2, otherwise the Slideshow 
                   on the Home page will be selected instead 
                   when clicked on. */
}

/* Icon Styling */
.newMsgCommentDotsIcon {
    background-color: #121212;
    color: white;
    padding: 6px 8px 6px 8px;
    font-size: 21px;
}
.newMsgIndicator {
    position: absolute;
    top: -11px;
    left: -18px;
    color: forestgreen;
    font-size: 13px;
}
.newMsgUpIcon {
    position: relative;
    right: -32px;
    background-color: #121212;
    color: white;
    padding: 6px 11px 6px 11px;
    font-size: 21px;
}

/* Character Styling */
.newMsgQuantity {
    color: forestgreen;
    font-weight: bold;
    position: relative;
    left: -35px;
    font-size: 21px;
}
.newMsgTitle {
    color: white;
    font-weight: bold;
    position: relative;
    left: -35px;
    font-size: 21px;
}

/**************************Chat Box***************************/

#chatTextArea {
    position: fixed;
    bottom: -440px;
    left: 0px;
    width: 325px;
    min-height: 440px;
    border: 5px solid #1a1a1a;
    background: white;
    z-index: 3;
}

#chatBoxClose {
    float: right;
    padding: 10px;
    cursor: pointer;
}

.chatPopupContent {
    position: fixed;
    bottom: 0;
    left: 0;
}

/*============================ END NEW MESSAGE BAR =============================*/

### Copy to Clipboard

Details.cshtml

 <dt class="col flex-md-row">
                  @Html.DisplayNameFor(model => model.Description)<i class="fa fa-clipboard" id="copyToClip" aria-hidden="true" onclick="copyToClipboard('@Model.Description')"></i>
                </dt>
                
async function copyToClipboard(copiedText) {
console.log(copiedText);
try {
     await navigator.clipboard.writeText(copiedText);
     console.log(copiedText);
    } catch (err) {
      console.error('Failed to copy: ', err);
      }

### CSS- CopyToClip

/*=================== Copy to Clipboard ===================*/

#copyToClip {
    padding-left: 5px;
}
#copyToClip:hover {
    cursor: pointer;
}

## Other Skills Learned
* Working with a team of developers in order to achieve a common goal. 
* Communicating with a team lead for accuracy, direction and support.
* Refining online researching skills.
* Time management.
  - During this project I had to juggle between a full time job and completing this project. The first week I stumbled and did not accomplish as much as I wanted, however I changed my working habits and completed a more challenging story in half the time the following week. It is very important to prioritize, maintain peace in your mind in order to perform logic and work. Once I dedicated the appropriate time and energy needed, I was able to succeed. 
* A love for front-end development.
  - This project really helped me build upon my love for front-end development! I love being able to see results quickly, play/change aestheics and test the product. 
* Confidence in research, even while doubting ability.
  - This project really showed me that to be successful, you must keep it simple and do the research. Software development is vast, there is much to know in every area and language. Not knowing something initially is just fine and if you research, validate and implement, there will be positive results!
