---
title: オンボーディングまたはオフボーディングの通知ルールを作成する
description: ローカルオンボーディングスクリプトまたはオフボード スクリプトが使用されている場合に通知を取得します。
keywords: オンボーディング、オフボード、ローカル、スクリプト、通知、ルール
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5dfdfc6d14add33154ed4c2370bca458e752125d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187233"
---
# <a name="create-a-notification-rule-when-a-local-onboarding-or-offboarding-script-is-used"></a><span data-ttu-id="f7a6a-104">ローカル オンボーディングスクリプトまたはオフボード スクリプトを使用する場合に通知ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="f7a6a-104">Create a notification rule when a local onboarding or offboarding script is used</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f7a6a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f7a6a-105">**Applies to:**</span></span>
- [<span data-ttu-id="f7a6a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f7a6a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f7a6a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7a6a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="f7a6a-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="f7a6a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f7a6a-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="f7a6a-110">ローカルオンボーディングまたはオフボード スクリプトが使用されている場合に通知を受け取る通知ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-110">Create a notification rule so that when a local onboarding or offboarding script is used, you'll be notified.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="f7a6a-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="f7a6a-111">Before you begin</span></span>
<span data-ttu-id="f7a6a-112">次のアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-112">You'll need to have access to:</span></span>
 - <span data-ttu-id="f7a6a-113">Microsoft Flow (Flowプラン 1 を使用します)。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-113">Microsoft Flow (Flow Plan 1 at a minimum).</span></span> <span data-ttu-id="f7a6a-114">詳細については、「価格設定[」Flowを参照してください](https://flow.microsoft.com/pricing/)。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-114">For more information, see [Flow pricing page](https://flow.microsoft.com/pricing/).</span></span>
 - <span data-ttu-id="f7a6a-115">Azure Table または SharePoint リストまたはライブラリ / SQL DB</span><span class="sxs-lookup"><span data-stu-id="f7a6a-115">Azure Table or SharePoint List or Library / SQL DB</span></span>

## <a name="create-the-notification-flow"></a><span data-ttu-id="f7a6a-116">通知フローの作成</span><span class="sxs-lookup"><span data-stu-id="f7a6a-116">Create the notification flow</span></span>

1. <span data-ttu-id="f7a6a-117">In [flow.microsoft.com](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f7a6a-117">In [flow.microsoft.com](https://flow.microsoft.com/).</span></span>

2. <span data-ttu-id="f7a6a-118">[スケジュール済 **み] の [>のフロー>から] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-118">Navigate to **My flows > New > Scheduled - from blank**.</span></span> 

    ![フローのイメージ](images/new-flow.png)


3. <span data-ttu-id="f7a6a-120">スケジュールされたフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-120">Build a scheduled flow.</span></span>
   1. <span data-ttu-id="f7a6a-121">フロー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-121">Enter a flow name.</span></span>
   2. <span data-ttu-id="f7a6a-122">開始時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-122">Specify the start and time.</span></span>
   3. <span data-ttu-id="f7a6a-123">頻度を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-123">Specify the frequency.</span></span> <span data-ttu-id="f7a6a-124">たとえば、5 分ごとに。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-124">For example, every 5 minutes.</span></span>

    ![通知フローのイメージ](images/build-flow.png)

4. <span data-ttu-id="f7a6a-126">+ボタンを選択して新しいアクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-126">Select the + button to add a new action.</span></span> <span data-ttu-id="f7a6a-127">新しいアクションは、Defender for Endpoint セキュリティ センター デバイス API への HTTP 要求です。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-127">The new action will be an HTTP request to the Defender for Endpoint security center device(s) API.</span></span> <span data-ttu-id="f7a6a-128">また、既定の "WDATP Connector" (アクション: "Machines - Get list of machines") に置き換えすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-128">You can also replace it with the out-of-the-box "WDATP Connector" (action: "Machines - Get list of machines").</span></span> 

    ![繰り返しのイメージとアクションの追加](images/recurrence-add.png)


5. <span data-ttu-id="f7a6a-130">次の HTTP フィールドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-130">Enter the following HTTP fields:</span></span>

   - <span data-ttu-id="f7a6a-131">メソッド: デバイスの一覧を取得する値として "GET" を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-131">Method: "GET" as a value to get the list of devices.</span></span>
   - <span data-ttu-id="f7a6a-132">URI: を入力します `https://api.securitycenter.microsoft.com/api/machines` 。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-132">URI: Enter `https://api.securitycenter.microsoft.com/api/machines`.</span></span>
   - <span data-ttu-id="f7a6a-133">認証: [Active Directory OAuth] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-133">Authentication: Select "Active Directory OAuth".</span></span>
   - <span data-ttu-id="f7a6a-134">テナント: サインインし、[アプリの登録 https://portal.azure.com ] Azure Active Directory >**に移動し**、テナント ID の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-134">Tenant: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and get the Tenant ID value.</span></span>
   - <span data-ttu-id="f7a6a-135">対象ユーザー: `https://securitycenter.onmicrosoft.com/windowsatpservice\`</span><span class="sxs-lookup"><span data-stu-id="f7a6a-135">Audience: `https://securitycenter.onmicrosoft.com/windowsatpservice\`</span></span>
   - <span data-ttu-id="f7a6a-136">クライアント ID: アプリ登録にサインインして、Azure Active Directory >に移動し、クライアント https://portal.azure.com ID の値を取得します。 </span><span class="sxs-lookup"><span data-stu-id="f7a6a-136">Client ID: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and  get the Client ID value.</span></span>
   - <span data-ttu-id="f7a6a-137">資格情報の種類: [シークレット] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-137">Credential Type: Select "Secret".</span></span>
   - <span data-ttu-id="f7a6a-138">シークレット: サインインして、アプリの登録Azure Active Directory >に移動し、テナント https://portal.azure.com ID の値を取得します。 </span><span class="sxs-lookup"><span data-stu-id="f7a6a-138">Secret: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and get the Tenant ID value.</span></span>

    ![HTTP 条件のイメージ](images/http-conditions.png)


6. <span data-ttu-id="f7a6a-140">[新しいアクションの追加] を選択して新しい手順を追加 **し** 、[データ操作] を検索 **し** 、[JSON の解析] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-140">Add a new step by selecting **Add new action** then search for **Data Operations** and select **Parse JSON**.</span></span>

    ![データ操作のイメージ](images/data-operations.png)

7. <span data-ttu-id="f7a6a-142">[コンテンツ] フィールドに **Body を追加** します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-142">Add Body in the **Content** field.</span></span>

    ![解析 JSON のイメージ](images/parse-json.png)

8. <span data-ttu-id="f7a6a-144">[サンプル ペイロード **を使用してスキーマを生成する] リンクを選択** します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-144">Select the **Use sample payload to generate schema** link.</span></span>

    ![ペイロードを使用した解析 json のイメージ](images/parse-json-schema.png)

9. <span data-ttu-id="f7a6a-146">次の JSON スニペットをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-146">Copy and paste the following JSON snippet:</span></span>

    ```
    {
        "type": "object",
        "properties": {
            "@@odata.context": {
                "type": "string"
            },
            "value": {
                "type": "array",
                "items": {
                    "type": "object",
                    "properties": {
                        "id": {
                            "type": "string"
                        },
                        "computerDnsName": {
                            "type": "string"
                        },
                        "firstSeen": {
                            "type": "string"
                        },
                        "lastSeen": {
                            "type": "string"
                        },
                        "osPlatform": {
                            "type": "string"
                        },
                        "osVersion": {},
                        "lastIpAddress": {
                            "type": "string"
                        },
                        "lastExternalIpAddress": {
                            "type": "string"
                        },
                        "agentVersion": {
                            "type": "string"
                        },
                        "osBuild": {
                            "type": "integer"
                        },
                        "healthStatus": {
                            "type": "string"
                        },
                        "riskScore": {
                            "type": "string"
                        },
                        "exposureScore": {
                            "type": "string"
                        },
                        "aadDeviceId": {},
                        "machineTags": {
                            "type": "array"
                        }
                    },
                    "required": [
                        "id",
                        "computerDnsName",
                        "firstSeen",
                        "lastSeen",
                        "osPlatform",
                        "osVersion",
                        "lastIpAddress",
                        "lastExternalIpAddress",
                        "agentVersion",
                        "osBuild",
                        "healthStatus",
                        "rbacGroupId",
                        "rbacGroupName",
                        "riskScore",
                        "exposureScore",
                        "aadDeviceId",
                        "machineTags"
                    ]
                }
            }
        }
    }

    ```

10.  <span data-ttu-id="f7a6a-147">JSON 呼び出しから値を抽出し、オンボードデバイスが /が既に登録されている場合は、SharePointリストに登録されています。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-147">Extract the values from the JSON call and check if the onboarded device(s) is / are already registered at the SharePoint list as an example:</span></span>
- <span data-ttu-id="f7a6a-148">はいの場合、通知はトリガーされません</span><span class="sxs-lookup"><span data-stu-id="f7a6a-148">If yes, no notification will be triggered</span></span>
- <span data-ttu-id="f7a6a-149">いいえの場合は、新しいオンボード デバイスが [SharePoint] リストに登録され、Defender for Endpoint 管理者に通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-149">If no, will register the new onboarded device(s) in the SharePoint list and a notification will be sent to the Defender for Endpoint admin</span></span>

    ![それぞれの適用イメージ](images/flow-apply.png)

    ![取得項目を持つ各項目に適用するイメージ](images/apply-to-each.png)

11. <span data-ttu-id="f7a6a-152">[ **条件]** で、次の式を追加します。"length(body('Get_items')?'value']) をクリックし、条件を 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-152">Under **Condition**, add the following expression: "length(body('Get_items')?['value'])" and set the condition to equal to 0.</span></span>

    <span data-ttu-id="f7a6a-153">![各条件に適用されるイメージ](images/apply-to-each-value.png)</span><span class="sxs-lookup"><span data-stu-id="f7a6a-153">![Image of apply to each condition](images/apply-to-each-value.png)</span></span>  
    <span data-ttu-id="f7a6a-154">![condition1 ](images/conditions-2.png) 
     ![ のイメージ condition2 のイメージ](images/condition3.png)</span><span class="sxs-lookup"><span data-stu-id="f7a6a-154">![Image of condition1](images/conditions-2.png) 
    ![Image of condition2](images/condition3.png)</span></span>  
<span data-ttu-id="f7a6a-155">![送信メールの画像](images/send-email.png)</span><span class="sxs-lookup"><span data-stu-id="f7a6a-155">![Image of send email](images/send-email.png)</span></span>

## <a name="alert-notification"></a><span data-ttu-id="f7a6a-156">アラート通知</span><span class="sxs-lookup"><span data-stu-id="f7a6a-156">Alert notification</span></span>
<span data-ttu-id="f7a6a-157">次の図は、電子メール通知の例です。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-157">The following image is an example of an email notification.</span></span>

![電子メール通知の画像](images/alert-notification.png)


## <a name="tips"></a><span data-ttu-id="f7a6a-159">ヒント</span><span class="sxs-lookup"><span data-stu-id="f7a6a-159">Tips</span></span>

- <span data-ttu-id="f7a6a-160">lastSeen のみを使用してここでフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-160">You can filter here using lastSeen only:</span></span>
    - <span data-ttu-id="f7a6a-161">60 分ごとに:</span><span class="sxs-lookup"><span data-stu-id="f7a6a-161">Every 60 min:</span></span>
      - <span data-ttu-id="f7a6a-162">過去 7 日間に最後に見られたすべてのデバイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-162">Take all devices last seen in the past 7 days.</span></span> 

- <span data-ttu-id="f7a6a-163">デバイスごとに次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-163">For each device:</span></span> 
    - <span data-ttu-id="f7a6a-164">最後に表示されたプロパティが [-7 日、 -7days + 60 分] の 1 時間間隔にある場合は、-> オフボードの可能性を警告します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-164">If last seen property is on the one hour interval of [-7 days, -7days + 60 minutes ] -> Alert for offboarding possibility.</span></span>
    - <span data-ttu-id="f7a6a-165">最初に表示された場合は、過去 1 時間のオンボーディング>アラートを表示します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-165">If first seen is on the past hour -> Alert for onboarding.</span></span>

<span data-ttu-id="f7a6a-166">このソリューションでは、重複するアラートが発生しない: 多数のデバイスを持つテナントがあります。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-166">In this solution you will not have duplicate alerts: There are tenants that have numerous devices.</span></span> <span data-ttu-id="f7a6a-167">これらのデバイスをすべて取得すると、非常にコストが高く、ページングが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-167">Getting all those devices might be very expensive and might require paging.</span></span>

<span data-ttu-id="f7a6a-168">次の 2 つのクエリに分割できます。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-168">You can split it to two queries:</span></span> 
1.  <span data-ttu-id="f7a6a-169">オフボードの場合は、OData を使用してこの間隔のみを$filter条件が満たされた場合にのみ通知します。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-169">For offboarding take only this interval using the OData $filter and only notify if the conditions are met.</span></span>
2.  <span data-ttu-id="f7a6a-170">過去 1 時間に最後に見られたすべてのデバイスを使用し、最初に表示されたプロパティを確認します (最初に表示されたプロパティが過去 1 時間の場合は、最後に表示されたプロパティも表示されている必要があります)。</span><span class="sxs-lookup"><span data-stu-id="f7a6a-170">Take all devices last seen in the past hour and check first seen property for them (if the first seen property is on the past hour, the last seen must be there too).</span></span> 

