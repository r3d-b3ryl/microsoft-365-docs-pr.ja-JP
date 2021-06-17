---
title: イベント ハブを構成する
description: イベント ハブを構成する方法の詳細
keywords: イベント ハブ、構成、分析情報
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985662"
---
# <a name="configure-your-event-hub"></a><span data-ttu-id="37516-104">イベント ハブを構成する</span><span class="sxs-lookup"><span data-stu-id="37516-104">Configure your Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="37516-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="37516-105">**Applies to:**</span></span>
- [<span data-ttu-id="37516-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37516-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="37516-107">イベント ハブがイベントを外部から取り込むMicrosoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="37516-107">Learn how to configure your Event Hub so that it can ingest events from Microsoft 365 Defender.</span></span>


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a><span data-ttu-id="37516-108">Event Hub サブスクリプションで必要なリソース プロバイダーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="37516-108">Setup the required Resource Provider in the Event Hub subscription</span></span>


1. <span data-ttu-id="37516-109">[Azure portal](https://portal.azure.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="37516-109">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
1. <span data-ttu-id="37516-110">[ **サブスクリプション \> ] を選択 ***します 。 イベント ハブ*** が } リソース プロバイダーに展開されるサブスクリプション \> を選択します**。</span><span class="sxs-lookup"><span data-stu-id="37516-110">Select **Subscriptions \> {***Select the subscription the event hub will be deployed to***} \> Resource providers**.</span></span>
1. <span data-ttu-id="37516-111">**Microsoft.インサイト プロバイダーが登録** されているを確認します。</span><span class="sxs-lookup"><span data-stu-id="37516-111">Verify that the **Microsoft.Insights** Provider is registered.</span></span> <span data-ttu-id="37516-112">それ以外の場合は、登録します。</span><span class="sxs-lookup"><span data-stu-id="37516-112">Otherwise, register it.</span></span>

![リソース プロバイダーのMicrosoft Azure](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a><span data-ttu-id="37516-114">アプリAzure Active Directoryのセットアップ</span><span class="sxs-lookup"><span data-stu-id="37516-114">Setup Azure Active Directory App Registration</span></span>


><span data-ttu-id="37516-115">![メモ]管理者以外のユーザーがアプリを登録Azure Active Directoryするには、管理者ロールまたは管理者以外のユーザー (AAD) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37516-115">![NOTE] You must have Administrator role or Azure Active Directory (AAD) must be set to allow non-Administrators to register apps.</span></span> <span data-ttu-id="37516-116">サービス プリンシパルに役割を割り当てるには、所有者またはユーザー アクセス管理者の役割も必要です。</span><span class="sxs-lookup"><span data-stu-id="37516-116">You must also have an Owner or User Access Administrator role to assign the service principal a role.</span></span>  
><span data-ttu-id="37516-117">詳細については、「ポータルで Azure AD アプリ & サービス プリンシパルを作成する - Microsoft Docs Microsoft ID プラットフォーム[ \| を参照してください](/azure/active-directory/develop/howto-create-service-principal-portal)。</span><span class="sxs-lookup"><span data-stu-id="37516-117">For more information, see [Create an Azure AD app & service principal in the portal - Microsoft identity platform \| Microsoft Docs](/azure/active-directory/develop/howto-create-service-principal-portal).</span></span>

1. <span data-ttu-id="37516-118">[アプリの登録] [新しい登録] で新しい登録 (本質的に **サービス プリンシパルをAzure Active Directory \> 作成 \> します。**</span><span class="sxs-lookup"><span data-stu-id="37516-118">Create a new registration (which inherently creates a service principal) in **Azure Active Directory \> App registrations \> New registration.**</span></span>

1. <span data-ttu-id="37516-119">[名前] だけでフォームに入力します (リダイレクト URI は必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="37516-119">Fill out the form with just the Name (no Redirect URI is required).</span></span>

    ![アプリケーションの登録イメージ](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![概要情報の画像](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. <span data-ttu-id="37516-122">[証明書] をクリックしてシークレットを作成 **&新しいクライアント \> シークレットを作成します**。</span><span class="sxs-lookup"><span data-stu-id="37516-122">Create a secret by clicking on **Certificates & secrets \> New client secret**:</span></span>

    ![証明書とシークレットのイメージ](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
><span data-ttu-id="37516-124">**クライアント シークレットに再度** アクセスできないので、必ず保存してください。</span><span class="sxs-lookup"><span data-stu-id="37516-124">**You won't be able to access the client secret again so make sure to save it**.</span></span>

## <a name="setup-event-hub-namespace"></a><span data-ttu-id="37516-125">Setup Event Hub 名前空間</span><span class="sxs-lookup"><span data-stu-id="37516-125">Setup Event Hub namespace</span></span>


1. <span data-ttu-id="37516-126">イベント ハブ名前空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="37516-126">Create an Event Hub Namespace:</span></span>

    <span data-ttu-id="37516-127">[Event **Hubs \> Add]** に移動し、予想される負荷に適した価格レベル、スループット 単位、自動インフレート (標準の価格と機能が必要) を選択します。</span><span class="sxs-lookup"><span data-stu-id="37516-127">Go **to Event Hubs \> Add** and select the pricing tier, throughput units and Auto-Inflate (requires standard pricing and under features) appropriate for the load you are expecting.</span></span>  
    <span data-ttu-id="37516-128">詳細については[、「Pricing - Event Hubs Microsoft Azure \| ](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="37516-128">For more information, see [Pricing - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span></span>

    >[!NOTE]
    > <span data-ttu-id="37516-129">既存のイベント ハブを使用できますが、スループットとスケーリングは名前空間レベルで設定されます。そのため、イベント ハブは、その名前空間に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37516-129">You can use an existing event hub, but the throughput and scaling are set at the namespace level so it is recommended to place an event hub in itsown namespace.</span></span>

   ![イベント ハブのネーム スペースのイメージ](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. <span data-ttu-id="37516-131">また、このイベント ハブ名前空間のリソース ID も必要です。</span><span class="sxs-lookup"><span data-stu-id="37516-131">You will also need the Resource ID of this Event Hub Namespace.</span></span> <span data-ttu-id="37516-132">Azure Event Hubs 名前空間ページの [プロパティ] に移動 \> します。</span><span class="sxs-lookup"><span data-stu-id="37516-132">Go to your Azure Event Hubs namespace page \> Properties.</span></span> <span data-ttu-id="37516-133">[リソース ID] の下のテキストをコピーし、以下の [M365 構成] セクションで使用するために記録します。</span><span class="sxs-lookup"><span data-stu-id="37516-133">Copy the text under Resource ID and record it for use during the M365 Configuration section below.</span></span> 

    ![プロパティのイメージ](../../media/759498162a4e93cbf17c4130d704d164.png)

1. <span data-ttu-id="37516-135">イベント ハブ名前空間を作成したら、App Registration Service Principal を Reader、Azure Event Hubs Data Receiver、および投稿者として Microsoft 365 Defender にログインするユーザーを追加する必要があります (これは、リソース グループまたはサブスクリプション レベルでも実行できます)。</span><span class="sxs-lookup"><span data-stu-id="37516-135">Once the Event Hub Namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver, and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span>

    <span data-ttu-id="37516-136">これは、Event **Hubs 名前空間 \> アクセス制御 (IAM) \> [役割** の割り当て] の [追加と確認] **で行います**。</span><span class="sxs-lookup"><span data-stu-id="37516-136">This is done in **Event Hubs Namespace \> Access Control (IAM) \> Add** and verify under **Role assignments**:</span></span>

    ![アクセス制御のイメージ](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a><span data-ttu-id="37516-138">セットアップ イベント ハブ</span><span class="sxs-lookup"><span data-stu-id="37516-138">Setup Event Hub</span></span>


<span data-ttu-id="37516-139">**オプション 1:**</span><span class="sxs-lookup"><span data-stu-id="37516-139">**Option 1:**</span></span>

<span data-ttu-id="37516-140">名前空間内にイベント ハブを作成し、エクスポートするために選択したイベントの種類 (テーブル) はすべて、この 1 つのイベント **ハブに** 書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="37516-140">You can create an Event Hub within your Namespace and **all** the Event Types (Tables) you select to export will be written into this **one** Event Hub.</span></span>

<span data-ttu-id="37516-141">**オプション 2:**</span><span class="sxs-lookup"><span data-stu-id="37516-141">**Option 2:**</span></span>

<span data-ttu-id="37516-142">すべてのイベントの種類 (テーブル) を 1 つのイベント ハブにエクスポートする代わりに、各テーブルをイベント ハブ名前空間内の別のイベント ハブ (イベントの種類ごとに 1 つのイベント ハブ) にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="37516-142">Instead of exporting all the Event Types (Tables) into one Event Hub, you can export each table into a different Event Hub inside your Event Hub Namespace (one Event Hub per Event Type).</span></span>  

<span data-ttu-id="37516-143">このオプションでは、Microsoft 365 Defenderイベント ハブを作成します。</span><span class="sxs-lookup"><span data-stu-id="37516-143">In this option, Microsoft 365 Defender will create Event Hubs for you.</span></span>  
>[!NOTE]
> <span data-ttu-id="37516-144">イベント ハブ クラスターの一部ではないイベントハブ名前空間を使用している場合は、Azure のイベント ハブ名前空間あたり 10 イベント ハブの制限により、定義した各エクスポート 設定 でエクスポートするイベント の種類 (テーブル) を最大 10 つまで選択できます。</span><span class="sxs-lookup"><span data-stu-id="37516-144">If you are using an Event Hub Namespace that is **not** part of an Event Hub Cluster, you will only be able to choose up to 10 Event Types (Tables) to export in each Export Settings you define, due to an Azure limitation of 10 Event Hubs per Event Hub Namespace.</span></span>

<span data-ttu-id="37516-145">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37516-145">For example:</span></span>

![イベント ハブの例のイメージ](../../media/005c1f6c10c34420d387f594987f9ffe.png)

<span data-ttu-id="37516-147">このオプションを選択した場合は、[電子メール テーブルを送信するMicrosoft 365 Defender[の構成] セクションにスキップ](#configure-microsoft-365-defender-to-send-email-tables)できます。</span><span class="sxs-lookup"><span data-stu-id="37516-147">If you choose this option, you can skip to the [Configure Microsoft 365 Defender to send email tables](#configure-microsoft-365-defender-to-send-email-tables) section.</span></span>

<span data-ttu-id="37516-148">[イベント ハブ] + [イベント ハブ] を選択して、名前空間内に **\> イベント ハブを作成します**。</span><span class="sxs-lookup"><span data-stu-id="37516-148">Create an Event Hub within your Namespace by selecting **Event Hubs \> + Event Hub**.</span></span>

<span data-ttu-id="37516-149">パーティション数を使用すると、並列処理を使用してスループットを増やし、必要な負荷に基づいてこの数を増やしてください。</span><span class="sxs-lookup"><span data-stu-id="37516-149">The Partition Count allows for additional throughput via parallelism, so it is recommended to increase this number based on the load you are expecting.</span></span>  
<span data-ttu-id="37516-150">既定のメッセージの保持とキャプチャの値は 1 とオフをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="37516-150">Default Message Retention and Capture values of 1 and Off are recommended.</span></span>

![Create Event Hub のイメージ](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

<span data-ttu-id="37516-152">このイベント ハブ (名前空間ではない) では、送信、リッスンクレームを使用して共有アクセス ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37516-152">For this Event Hub (not namespace) you will need to configure a Shared Access Policy with Send, Listen Claims.</span></span> <span data-ttu-id="37516-153">[イベント ハブ共有アクセス ポリシー] **\> + \> [** 追加] をクリックし、ポリシー名 (他の場所では使用されません) を指定し、[送信とリッスン]**を\*\*\*\*オンにしてください**。</span><span class="sxs-lookup"><span data-stu-id="37516-153">Click on your **Event Hub \> Shared access policies \> + Add** and then give it a Policy name (not used elsewhere) and check **Send** and **Listen**.</span></span>

![共有アクセス ポリシーのイメージ](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a><span data-ttu-id="37516-155">電子メール Microsoft 365 Defender送信する方法を構成する</span><span class="sxs-lookup"><span data-stu-id="37516-155">Configure Microsoft 365 Defender to send email tables</span></span>


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a><span data-ttu-id="37516-156">イベント ハブMicrosoft 365 Defender Splunk に電子メール テーブルを送信するセットアップ</span><span class="sxs-lookup"><span data-stu-id="37516-156">Setup Microsoft 365 Defender send Email tables to Splunk via Event Hub</span></span>


1. <span data-ttu-id="37516-157">次のMicrosoft 365 Defender <https://security.microsoft.com> 要件を満たすアカウントを使用して、アカウントにログインします。</span><span class="sxs-lookup"><span data-stu-id="37516-157">Login to Microsoft 365 Defender at <https://security.microsoft.com> with an account that meets all the following role requirements:</span></span>

    - <span data-ttu-id="37516-158">エクスポートするイベント ハブの Event Hub *名前空間* リソース レベル以上の共同作成者ロール。</span><span class="sxs-lookup"><span data-stu-id="37516-158">Contributor role at the Event Hub *Namespace* Resource level or higher for the Event Hub that you will be exporting to.</span></span> <span data-ttu-id="37516-159">この場合、設定を保存しようとするときにエクスポート エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="37516-159">Without this you will get an export error when you try to save the settings.</span></span>

    - <span data-ttu-id="37516-160">テナントのグローバル管理者またはセキュリティ管理者の役割は、Microsoft 365 Defender Azure に関連付けされます。</span><span class="sxs-lookup"><span data-stu-id="37516-160">Global Admin or Security Admin Role on the tenant tied to Microsoft 365 Defender and Azure.</span></span>

    ![セキュリティ ポータルのイメージ](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. <span data-ttu-id="37516-162">[生データ **のエクスポート] \> + [追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="37516-162">Click on **Raw Data Export \> +Add**.</span></span>

    <span data-ttu-id="37516-163">これで、上記で記録したデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="37516-163">You will now use the data that your recorded above.</span></span>

    <span data-ttu-id="37516-164">**名前**: これはローカルであり、環境で動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37516-164">**Name**: This is local and should be whatever works in your environment.</span></span>

    <span data-ttu-id="37516-165">**イベント をイベント ハブに転送する**: このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="37516-165">**Forward events to event hub**: Select this checkbox.</span></span>

    <span data-ttu-id="37516-166">**Event-Hub リソース ID**: これは、イベント ハブのセットアップ時に上記で記録したイベント ハブ名前空間リソース ID です。</span><span class="sxs-lookup"><span data-stu-id="37516-166">**Event-Hub Resource ID**: This is the Event Hub Namespace Resource ID you  recorded above when you setup the Event Hub.</span></span>

    <span data-ttu-id="37516-167">**イベント ハブ名**: イベント ハブ名前空間内にイベント ハブを作成した場合は、上記で記録したイベント ハブ名を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="37516-167">**Event-Hub name**:  If you created an Event Hub inside your Event Hub Namespace, paste the Event Hub  name you recorded above.</span></span>

    <span data-ttu-id="37516-168">イベント の種類 (テーブル) Microsoft 365 Defenderイベント ハブを作成する場合は、このフィールドを空のままにします。</span><span class="sxs-lookup"><span data-stu-id="37516-168">If you choose to let Microsoft 365 Defender to create Event Hubs per Event Types  (Tables) for you, leave this field empty.</span></span>

    <span data-ttu-id="37516-169">**イベントの種類**: イベント ハブに転送し、カスタム アプリに転送する高度なハンティング テーブルを選択します。</span><span class="sxs-lookup"><span data-stu-id="37516-169">**Event Types**: Select the Advanced Hunting tables that you want to forward to the Event Hub and then on to your custom app.</span></span> <span data-ttu-id="37516-170">アラート テーブルは Microsoft 365 Defender から、デバイス テーブルは Microsoft Defender for Endpoint (EDR) から、電子メール テーブルは Microsoft Defender から Office 365。</span><span class="sxs-lookup"><span data-stu-id="37516-170">Alert tables are from Microsoft 365 Defender, Devices tables are from Microsoft Defender for Endpoint (EDR), and Email tables are from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="37516-171">電子メール イベントは、すべての電子メール トランザクションを記録します。</span><span class="sxs-lookup"><span data-stu-id="37516-171">Email Events records all Email Transactions.</span></span> <span data-ttu-id="37516-172">URL (SafeLinks)、添付ファイル (セーフ 添付ファイル)、配信後イベント (ZAP) も記録され、[NetworkMessageId] フィールドの [電子メール イベント] に参加できます。</span><span class="sxs-lookup"><span data-stu-id="37516-172">The URL (SafeLinks), Attachment (Safe Attachments) and Post Delivery Events (ZAP) are also recorded and can be joined to the Email Events on the NetworkMessageId field.</span></span>

    ![ストリーミング API 設定のイメージ](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. <span data-ttu-id="37516-174">[送信] をクリック **してください**。</span><span class="sxs-lookup"><span data-stu-id="37516-174">Make sure to click **Submit**.</span></span>

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a><span data-ttu-id="37516-175">イベントがイベント ハブにエクスポートされるのを確認する</span><span class="sxs-lookup"><span data-stu-id="37516-175">Verify that the events are being exported to the Event Hub</span></span>


<span data-ttu-id="37516-176">イベントがイベント ハブに送信されるのを確認するには、基本的な高度なハンティング クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="37516-176">You can verify that events are being sent to the Event Hub by running a basic Advanced Hunting query.</span></span> <span data-ttu-id="37516-177">[ハン **ティング \> の高度な検索 \> クエリ] を** 選択し、次のクエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="37516-177">Select **Hunting \> Advanced Hunting \> Query** and enter the following query:</span></span>

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

<span data-ttu-id="37516-178">これにより、他のすべてのテーブルに参加した過去 1 時間に受信されたメールの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="37516-178">This will show you how many emails were received in the last hour joined across all the other tables.</span></span> <span data-ttu-id="37516-179">また、イベント ハブにエクスポートできるイベントが表示される場合も表示されます。</span><span class="sxs-lookup"><span data-stu-id="37516-179">It will also show you if you are seeing events that could be exported to the event hub.</span></span> <span data-ttu-id="37516-180">この数に 0 が表示されている場合は、イベント ハブにデータが表示されません。</span><span class="sxs-lookup"><span data-stu-id="37516-180">If this count shows 0 then you won't see any data going out to the Event Hub.</span></span>

![高度な狩猟のイメージ](../../media/c305e57dc6f72fa9eb035943f244738e.png)

<span data-ttu-id="37516-182">エクスポートするデータが含まれますのを確認したら、イベント ハブを表示して、メッセージが受信されるのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="37516-182">Once you have verified there is data to export, you can view the Event Hub to verify that messages are incoming.</span></span> <span data-ttu-id="37516-183">これには最大 1 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="37516-183">This can take up to one hour.</span></span> 
 
1. <span data-ttu-id="37516-184">Azure で、[イベント ハブ] [名前空間イベント ハブ] [イベント **\> \> \> ハブ] の [クリック] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="37516-184">In Azure, go to **Event Hubs \> Click on the Namespace \> Event Hubs \> Click on the Event Hub**.</span></span>  
1. <span data-ttu-id="37516-185">[ **概要]** で下にスクロールし、[メッセージ] グラフに [受信メッセージ] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="37516-185">Under **Overview**, scroll down and in the Messages graph you should see Incoming Messages.</span></span> <span data-ttu-id="37516-186">結果が表示されていない場合、カスタム アプリが取り込むメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="37516-186">If you don't see any results, then there will be no messages for your custom app to ingest.</span></span>

    ![メッセージを含む [概要] タブのイメージ](../../media/e88060e315d76e74269a3fc866df047f.png)
