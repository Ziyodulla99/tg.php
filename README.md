
<?php
ob_start();
error_reporting(0);

define("AlijonovUz",'5739773016:AAGOhCfpwdj4nbPheAf9YF0Lrt4uadiTDG8');
$admin = "2105500573";
$user = "AlijonovUz";
$bot = bot('getme',['bot'])->result->username;

function bot($method,$datas=[]){
	$url = "https://api.telegram.org/bot".AlijonovUz."/".$method;
$ch = curl_init();
curl_setopt($ch,CURLOPT_URL,$url);
curl_setopt($ch,CURLOPT_RETURNTRANSFER,true);
curl_setopt($ch,CURLOPT_POSTFIELDS,$datas);
$res = curl_exec($ch);
if(curl_error($ch)){
	var_dump(curl_error($ch));
	}else{
		return json_decode($res);
	}
}

function joinchat($id){
     global $mid;
$kanal = "By_Alik";
$ret = bot("getChatMember",[
         "chat_id"=>"@".$kanal."",
         "user_id"=>$id,
         ]);
$stat = $ret->result->status;
         if(($stat =="creator" or $stat =="administrator" or $stat =="member")){
      return true;
         }else{
     bot('sendMessage',[
'chat_id'=>$id,
'text'=>"<b>⭐️ Premium olish uchun tarqatishda bizga yordam beradigan homiylarimizga obuna bo'ling:</b>",
'parse_mode'=>"html",
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>"❌ $kanal",'url'=>"https://t.me/$kanal"]],
[['text'=>"✅ Tekshirish",'callback_data'=>"tekshir"]]
]
])
]);
}
}

//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!


$update = json_decode(file_get_contents('php://input'));
$message = $update->message;
$text = $message->text;
$cid = $message->chat->id;
$mid = $message->message_id;
$name = $message->from->first_name;
$username = $message->from->username;

$data = $update->callback_query->data;
$qid = $update->callback_query->id;
$cid2 = $update->callback_query->message->chat->id;
$mid2 = $update->callback_query->message->message_id;
$calluser = $update->callback_query->from->username;
$callname = $update->callback_query->from->first_name;

$odam = file_get_contents("odam/$cid.txt");
$baza = file_get_contents("azo.dat");
mkdir("odam");

function replyKeyboard($keyboard) {
    return json_encode([
        'resize_keyboard'=>true,
        'keyboard'=> $keyboard
    ]);
}

$menu = replyKeyboard([
[['text'=>"✅ Davom etish"]],
]);

$premium = replyKeyboard([
[['text'=>"🥇 PREMIUM 1 yilga"]],
[['text'=>"🥈 PREMIUM 3 oyga"]],
[['text'=>"🥉 PREMIUM 1 oyga"]],
]);

$keyingi = replyKeyboard([
[['text'=>"▶️ Keyingi"]],
]);
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
if($text == "/start"){
	bot('sendPhoto',[
	'chat_id'=>$cid,
	'photo'=>"https://t.me/NewBazaUz/6",
	'caption'=>"👋 Salom <b>$name</b>\n\nPremium ishga tushirilishi munosabati bilan biz hamma uchun global sovg'a uyushtirmoqdamiz! Shoshiling va sovg'angizni oling!",
'parse_mode'=>'html',
'reply_markup'=>$menu,
]);
}

	if(isset($message)){
$odam = file_get_contents("odam/$cid.txt");
$kkd = $odam+0;
file_put_contents("odam/$cid.txt","$kkd");
}
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
if(isset($message)){
   $baza = file_get_contents("azo.dat");
   if(mb_stripos($baza,$cid) !==false){
   }else{
   $txt="\n$cid";
   $file=fopen("azo.dat","a");
   fwrite($file,$txt);
   fclose($file);
   }
}

//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
	if(mb_stripos($text,"/start")!==false){
$refid = explode(" ",$text);
$refid = $refid[1];
if(strlen($refid)>0 and $refid>0){
if($refid == $cid){
bot('sendPhoto',[
	'chat_id'=>$cid,
	'photo'=>"https://t.me/NewBazaUz/6",
	'caption'=>"👋 Salom <b>$name</b>\n\nPremium ishga tushirilishi munosabati bilan biz hamma uchun global sovg'a uyushtirmoqdamiz! Shoshiling va sovg'angizni oling!",
'parse_mode'=>'html',
'reply_markup'=>$menu,
]);
}else{
if(mb_stripos($user_id,"$cid")!==false){
bot('sendPhoto',[
	'chat_id'=>$cid,
	'photo'=>"https://t.me/NewBazaUz/6",
	'caption'=>"👋 Salom <b>$name</b>\n\nPremium ishga tushirilishi munosabati bilan biz hamma uchun global sovg'a uyushtirmoqdamiz! Shoshiling va sovg'angizni oling!",
'parse_mode'=>'html',
'reply_markup'=>$menu,
]);
}else{
$odam = file_get_contents("odam/$refid.txt");
$b = $odam + 1;
file_put_contents("odam/$refid.txt","$b");
bot('sendPhoto',[
	'chat_id'=>$cid,
	'photo'=>"https://t.me/NewBazaUz/6",
	'caption'=>"👋 Salom <b>$name</b>\n\nPremium ishga tushirilishi munosabati bilan biz hamma uchun global sovg'a uyushtirmoqdamiz! Shoshiling va sovg'angizni oling!",
'parse_mode'=>'html',
'reply_markup'=>$menu,
]);
bot('SendMessage',[
'chat_id'=>$refid,
'text'=>"✅ <b>Sizning havolangiz orqali yangi odam qo'shildi!</b>",
'parse_mode'=>'html',
]);
}
}
}
}

//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
if($text == "✅ Davom etish"){
bot('SendPhoto',[
'chat_id'=>$cid,
'photo'=>"https://t.me/NewBazaUz/8",
'caption'=>"🎁 <b>Mukofot olishni istagan davrni tanlang:</b>",
'parse_mode'=>'html',
'reply_markup'=>$premium,
]);
}

if($text == "🥇 PREMIUM 1 yilga" and joinchat($cid)==true){
	bot('SendPhoto',[
	'chat_id'=>$cid,
	'photo'=>"https://t.me/NewBazaUz/7",
	'caption'=>"🎉 <b>Bitta qiyinchilik qoldi! Noyob havolangiz orqali doʻstlaringizni taklif qiling:</b> https://t.me/$bot?start=$cid\n\n<b>Siz taklif qildingiz: $odam/20</b>",
	'parse_mode'=>'html',
	'reply_markup'=>$keyingi
	]);
}

//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
if($text == "🥈 PREMIUM 3 oyga" and joinchat($cid)==true){
	bot('SendPhoto',[
	'chat_id'=>$cid,
   'photo'=>"https://t.me/NewBazaUz/7",
	'caption'=>"🎉 <b>Bitta qiyinchilik qoldi! Noyob havolangiz orqali doʻstlaringizni taklif qiling:</b> https://t.me/$bot?start=$cid\n\n<b>Siz taklif qildingiz: $odam/20</b>",
	'parse_mode'=>'html',
	'reply_markup'=>$keyingi
	]);
}

if($text == "🥉 PREMIUM 1 oyga" and joinchat($cid)==true){
	bot('SendPhoto',[
	'chat_id'=>$cid,
   'photo'=>"https://t.me/NewBazaUz/7",
	'caption'=>"🎉 <b>Bitta qiyinchilik qoldi! Noyob havolangiz orqali doʻstlaringizni taklif qiling:</b> https://t.me/$bot?start=$cid\n\n<b>Siz taklif qildingiz: $odam/20</b>",
	'parse_mode'=>'html',
	'reply_markup'=>$keyingi
	]);
}
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
if($text == "▶️ Keyingi" and joinchat($cid)==true){
	if($odam == "20"){
	bot('SendMessage',[
	'chat_id'=>$cid,
	'text'=>"🎉 Tabriklaymiz <b>$name!</b>\n\nSiz botimizga 20 ta do'stingizni taklif qildingiz va PREMIUM sovg'asini yutib oldingiz. 24 soat ichida adminlar siz bilan bog'lanishadi.\n\n⏱ <b>Iltimos kuting...</b>",
	'parse_mode'=>'html',
'reply_markup'=>$menu,
	]);
	bot('SendMessage',[
	'chat_id'=>$admim,
	'text'=>"<b>Ushbu foydalanuvchi botga 20 ta do'stini taklif qildi va PREMIUM sovg'asini yutib oldi.
	
	Foydalanuvchi:</b> <a href='https://t.me/$username'>$cid</a>",
	'parse_mode'=>'html',
	'disable_web_page_preview'=>true,
	]);
unlink("odam/$cid.txt");
}else{
	bot('SendPhoto',[
	'chat_id'=>$cid,
	'photo'=>"https://t.me/NewBazaUz/7",
	'caption'=>"🎉 <b>Bitta qiyinchilik qoldi! Noyob havolangiz orqali doʻstlaringizni taklif qiling:</b> https://t.me/$bot?start=$cid\n\n<b>Siz taklif qildingiz: $odam/20</b>",
	'parse_mode'=>'html',
	]);
}
}
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
if($data == "tekshir"){
	if(joinchat($cid2)==true){
$odam = file_get_contents("odam/$cid2.txt");
	bot('deleteMessage',[
	'chat_id'=>$cid2,
	'message_id'=>$mid2,
	]);
	bot('SendPhoto',[
	'chat_id'=>$cid2,
	'photo'=>"https://t.me/NewBazaUz/7",
	'caption'=>"🎉 <b>Bitta qiyinchilik qoldi! Noyob havolangiz orqali doʻstlaringizni taklif qiling:</b> https://t.me/$bot?start=$cid\n\n<b>Siz taklif qildingiz: $odam/20</b>",
'parse_mode'=>'html',
'reply_markup'=>$keyingi
	]);
}else{
bot('deleteMessage',[
	'chat_id'=>$cid2,
	'message_id'=>$mid2,
	]);
}
}
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!
//Manga @UzCodePHP kanaliga tarqatildi ushbu kod @AlijonovUz tomonidan tuzilgan!

?>
