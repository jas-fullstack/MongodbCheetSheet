<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Potta+One&family=Roboto:wght@100&display=swap"
        rel="stylesheet">
    <link rel="stylesheet" href="prism.css">
    <script src="prism.js"></script>
    <link rel="stylesheet" href="style.css">
    <title>HTML Cheatsheet by CodeWithHarry</title>
</head>

<body>
    <nav>
        <span class="logo"><img src="copy.png" alt=""></span>
        <div class="content center">
            Mongodb Chat sheet!
        </div>
    </nav>
    <div class="container">
        <ol>
            <!-- <li><b>HTML Boilerplate:</b> This is the basic html boilerplate code
                <pre class="language-html"><code>&lt;!DOCTYPE html&gt; &lt;html lang="en"&gt;
&lt;head&gt;
    &lt;meta charset="UTF-8"&gt;
    &lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
    &lt;title&gt;Document&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
    
&lt;/body&gt;
&lt;/html&gt; </code></pre>
            </li> -->
            <li><b></b> find and sort
                <pre class="language-js"><code>db.users.find().sort( { _id: -1 } ) </code></pre>
            </li>

            <li><b></b> Mongodb save or update
                <pre class="language-js"><code>
    await UserModel.update({ userId: request.user_id }, {
        $set: {
            userId: request.user_id,
            isFollowing : true,
            createdAt: new Date
        }
        }, {  upsert: true}); </code></pre>
            </li>

            <li><b></b> Mongo aggrigation , subquery , get data from other table based on condition
                <pre class="language-js"><code>
{
$lookup:
{
    from: "payments",
    let: { userId: "$userId", paymentStatus: "$paymentStatus" },
    pipeline: [
    {
        $match:
        {
        $expr:
        {
            $and:
            [
                { $eq: ["$$userId", "$userId"] },
                { $eq: ["$paymentStatus", "Paid"] }
            ]
        }
        }
    }
    ],
    as: "lastPayment"
}
}</code></pre>
            </li>



            <li><b></b> Mongo aggrigation , subquery , count number of results.
                <pre class="language-js">
            <b>pass number object e.g user </b>
<code>

{
    $project: {
        total_users: { $size: "$user" },
        
    }
    }
}</code></pre>
            </li>
<li><b></b> Simple lookup exampple
                <pre class="language-js">
<code>
{
    $lookup: {
        from: 'userdata',
        localField: 'from_main table',
        foreignField: 'from_userDataTable',
        as: 'userData',
    }
    },
</code>
</pre>
</li>

           

            


        </ol>
    </div>
</body>

</html>
