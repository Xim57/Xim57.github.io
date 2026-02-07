<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Be My Valentine?</title>
  <style>
      /*General Page Styling*/
      body {
        margin: 0;
        padding: 0;
        heigth: 100vh;
        display: flex;
        justify-content: center;
        alingn-items: center;
        background-color: #ffc0cb;
        font-family: 'Arial', sans-serif;
        overflow: hidden;
      }

      .container {
        text-align: center;
        z-index: 10;
        background: rgba(255, 255, 255, 0.8);
        padding: 40px;
        border-radius: 20px;
        box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        max-width: 90%;
      }

      h1 {
          color: #d32f2f;
          font-size: 2.5rem;
          margin-bottom: 30px;
      }
      .btn-group {
          display: flex;
          justify-content: center;
          align-items: center;
          gap: 20px;
          flex-wrap: wrap;
          min-height: 100px;
      }

      button {
          padding: 15px 30px;
          front-size: 1.2rem;
          border: none;
          border-radius: 50px;
          cursor: pointer;
          transition: transform 0.2s, background-color 0.2;
      }
      
      
