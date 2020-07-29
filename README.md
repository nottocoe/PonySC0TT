# PonySC0TT
For Homework Only
<!DOCTYPE html>
<head>
    <title>REST API TEST</title>
    <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>
    <style>
        #customers {
          font-family: "Trebuchet MS", Arial, Helvetica, sans-serif;
          border-collapse: collapse;
          width: 100%;
        }
        
        #customers td, #customers th {
          border: 1px solid #ddd;
          padding: 8px;
          text-align: center;
        }
        
        #customers tr:nth-child(even){background-color: #f2f2f2;}
        
        #customers tr:hover {background-color: #ddd;}
        
        #customers th {
          padding-top: 12px;
          padding-bottom: 12px;
          text-align: left;
          background-color: #4CAF50;
          color: white;
        }

        </style>
</head>
<body>
    <table id="customers">
        <thead>
            <tr>
                <th>id</th>
                <th>Name</th>
                <th>Year</th>
                <th>Color</th>
                <th>Pantone</th>
            </tr>
        </thead>
        <tbody>
        </tbody>
        </div>
    </table>
    <script>
        $(document).ready(function(){
            console.log("HTTP CODE 200");
            var i;
            $.ajax({
                url : "https://reqres.in/api/unknown",
                dataType : "json",
                success : (function(data){
                    console.log(data)
                    for(i = 0; i < data.data.length; i++){
                        var str = "<tr><td>" + data.data[i].id + "</td>" + 
                        "<td>" + data.data[i].name + "</td>" +
                        "<td>" + data.data[i].year + "</td>" +
                        "<td>" + data.data[i].color + "</td>" +
                        "<td>" + data.data[i].pantone_value + "</td></tr>";
                        $("#customers").append(str);
                    }
                })
            })

        });
    </script>
</body>
</html>
