# task-desk
список задач с добавлением и удалением
<!DOCTYPE html>
<html>
<head>
	<title>Приложение Список задач</title>
		<style type="text/css">
			img{
				width: 100px;			
			}
			body{
				background-color: black;==
				margin: 5px;
				padding: 0px;
			}
			#dom{
				text-align: auto;
				text-shadow: 2px 2px 3px red;
				font-size: 39px;
				color: gray;
			}
			#top{
				border: solid 0px; background-color: grey;
			}
			p{
				font-size: 30px;
			}
			.add{
				font-size: 30px;
			}
			#box{
				font-size: 30px;
			}
			#task{
				background-color: darkblue;
			}
		</style>
			<script type="text/javascript">
				function addItem(){
						var newItem = document.createElement("div");
						newItem.innerHTML = document.getElementById('box').value;
						newItem.onclick = removeItem;
						document.getElementById("list").appendChild(newItem);
						saveList();
				}
				function removeItem(){
						document.getElementById("list").removeChild(this);
						saveList();
				}
				function saveList() {
						localStorage.storedList = document.getElementById('list').innerHTML;
				}
				function loadList(){
						document.getElementById('list').innerHTML = localStorage.storedList;
						for (var i = 0; i < list.children.length; i++ ) {
							list.children[i].onclick = removeItem;
						}
					}
			</script>
</head>
<body>
	<div id="top">
	<p><img align="left" src="logo.jpg"></p><p align="center" id="dom">Дом волковых</p>
	<br>
	</div>
		<div id="task">
			<p>Задачи для выставки:</p>
			<input type="text" id="box" placeholder="Введи задачу">
			<br>
			<br>
			<input type="button" class="add" value="Добавить" onclick="addItem();">
			<br>
				<div id="list"></div>
					<script type="text/javascript">
						if (localStorage.storedList) {
							loadList();
				}
					</script>
		</div>
</body>
</html>
