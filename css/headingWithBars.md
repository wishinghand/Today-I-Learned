If you have a centered heading and want lines on either side that are responsive, use this HTML template:

`<div class="containerRow">
        <div class="headingBar"></div>
        <div class="heading">Latest Deals</div>
        <div class="headingBar"></div>
  </div>`

  and CSS (remember to prefx):
  `.headingBar{
    background-color: white;
    height: 5px;
    flex-grow: 1;
    flex-shrink: 0;
    margin-bottom: 20px;
}

.heading{
    margin-bottom: 20px;
    margin-left: 15px;
    margin-right: 15px;
    font-size: 1.2em;
    font-weight: bold;
}

.containerRow{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    align-content: center;
    align-items: center;
}`