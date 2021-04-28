# Til
2021-04-27
==========
DateTime
--------
DateTime.ToUniversalTime();
현재 DateTime 개체의 값을 UTC(협정 세계시)로 변환

long으로 정의된 변수를 DateTime으로 변환할 수 있다.


<pre>
<code>
DateTime startInput = Convert.ToDateTime(startTimeInput.text).AddHours(9).ToUniversalTime();
</code>
</pre>

Json
----
원하는 객체를 Json으로 변환하기 위해서는 JsonUtility사용이 필요하다. 단, Dictionary는 Json으로의 변환이 불가능하다.
구조체(class)를 Json으로 변환하고 싶을땐 JsonUtility.ToJson을 통해 Json화 가능하다.
다수의 구조체를 Json으로 변환하고 싶을땐 해당 구조체를 List형태로 가지고 있는 다른 하나의 class를 생성하여 해당 class를 Json화 시키면 된다.


<pre>
<code>
public class JsonPlayer
    {
        public string userNickname;
        
    }
    
public class PlayerList
    {
        public static List<JsonPlayer> jsonPlayers;
    }
  
var jsonPlayer = JsonUtility.ToJson(PlayerList.jsonPlayers);
</code>
</pre>

Json을 다시 class로 변환하고 싶을 땐 JsonUtility.FromJson을 통해 class화 가능하다. 단, 해당 Json에 맞는 구조체 형식이 있어야 한다.

<pre>
<code>
List<UserInfo> userLists = JsonUtility.FromJson<List<UserInfo>>(json);
</code>
</pre>
