---
title: Microsoft Defender for Endpoint のホスト ファイアウォール レポート
description: セキュリティ センターでファイアウォールレポートをホストMicrosoft 365表示します。
keywords: Windows Defender, ファイアウォール
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809306"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="d2e95-104">Microsoft Defender for Endpoint のホスト ファイアウォール レポート</span><span class="sxs-lookup"><span data-stu-id="d2e95-104">Host firewall reporting in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d2e95-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d2e95-105">**Applies to:**</span></span>
- [<span data-ttu-id="d2e95-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d2e95-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d2e95-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2e95-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="d2e95-108">管理者の場合は、ファイアウォール レポートをセキュリティ センターにホストMicrosoft 365[できます](https://security.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="d2e95-108">If you are an admin, you can now host firewall reporting to [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="d2e95-109">この機能を使用すると、サーバー 2019 Windows 10とWindowsレポートを一元的な場所から表示できます。</span><span class="sxs-lookup"><span data-stu-id="d2e95-109">This feature enables you to view Windows 10 and Windows Server 2019 firewall reporting from a centralized location.</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d2e95-110">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="d2e95-110">What do you need to know before you begin?</span></span> 

- <span data-ttu-id="d2e95-111">サーバー 2019 Windows 10またはWindowsする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2e95-111">You must be running Windows 10 or Windows Server 2019.</span></span>
- <span data-ttu-id="d2e95-112">デバイスを Microsoft Defender for Endpoint サービスにオンボードするには、こちらを参照 [してください](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="d2e95-112">To onboard devices to the Microsoft Defender for Endpoint service, see [here](onboard-configure.md).</span></span> 
- <span data-ttu-id="d2e95-113">セキュリティ センター Microsoft 365データの受信を開始するには、Advanced Security を使用して監査イベントを **有効Windows Defender ファイアウォール必要** があります。</span><span class="sxs-lookup"><span data-stu-id="d2e95-113">For Microsoft 365 security center to start receiving the data, you must enable **Audit Events** for Windows Defender Firewall with Advanced Security:</span></span> 
    - [<span data-ttu-id="d2e95-114">監査フィルター プラットフォーム のパケット ドロップ</span><span class="sxs-lookup"><span data-stu-id="d2e95-114">Audit Filtering Platform Packet Drop</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [<span data-ttu-id="d2e95-115">監査フィルター プラットフォーム接続</span><span class="sxs-lookup"><span data-stu-id="d2e95-115">Audit Filtering Platform Connection</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- <span data-ttu-id="d2e95-116">グループ ポリシー オブジェクト エディター、ローカル セキュリティ ポリシー、またはグループ ポリシー コマンドを使用して、これらのイベントauditpol.exeします。</span><span class="sxs-lookup"><span data-stu-id="d2e95-116">Enable these events by using Group Policy Object Editor, Local Security Policy, or the auditpol.exe commands.</span></span> <span data-ttu-id="d2e95-117">詳細については、こちらを参照 [してください](/windows/win32/fwp/auditing-and-logging)。</span><span class="sxs-lookup"><span data-stu-id="d2e95-117">For more information, see [here](/windows/win32/fwp/auditing-and-logging).</span></span> 
    - <span data-ttu-id="d2e95-118">2 つの PowerShell コマンドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d2e95-118">The two PowerShell commands are:</span></span>
        - <span data-ttu-id="d2e95-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="d2e95-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span></span> 
        - <span data-ttu-id="d2e95-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="d2e95-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span></span> 

## <a name="the-process"></a><span data-ttu-id="d2e95-121">プロセス</span><span class="sxs-lookup"><span data-stu-id="d2e95-121">The process</span></span>
> [!NOTE]
> <span data-ttu-id="d2e95-122">上記のセクションの指示に従い、早期プレビュー参加のためにデバイスを適切に構成してください。</span><span class="sxs-lookup"><span data-stu-id="d2e95-122">Make sure to follow the instructions from the section above and properly configure your devices for the early preview participation.</span></span>

- <span data-ttu-id="d2e95-123">イベントを有効にすると、Microsoft 365センターがデータの監視を開始します。</span><span class="sxs-lookup"><span data-stu-id="d2e95-123">After enabling the events, Microsoft 365 security center will start to monitor the data.</span></span>
    - <span data-ttu-id="d2e95-124">リモート IP、リモート ポート、ローカル ポート、ローカル IP、コンピューター名、受信接続と送信接続間のプロセス。</span><span class="sxs-lookup"><span data-stu-id="d2e95-124">Remote IP, Remote Port, Local Port, Local IP, Computer Name, Process across inbound and outbound connections.</span></span>
- <span data-ttu-id="d2e95-125">管理者は、ここでホストWindowsアクティビティを確認[できます](https://security.microsoft.com/firewall)。</span><span class="sxs-lookup"><span data-stu-id="d2e95-125">Admins can now see Windows host firewall activity [here](https://security.microsoft.com/firewall).</span></span>
    - <span data-ttu-id="d2e95-126">カスタム レポート スクリプトをダウンロードして、[](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)カスタム レポートを使用してアクティビティのWindows Defender ファイアウォールを監視することで、Power BI。</span><span class="sxs-lookup"><span data-stu-id="d2e95-126">Additional reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 
    - <span data-ttu-id="d2e95-127">データが反映されるまで最大 12 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d2e95-127">It can take up to 12 hours before the data is reflected.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="d2e95-128">サポートされるシナリオ</span><span class="sxs-lookup"><span data-stu-id="d2e95-128">Supported scenarios</span></span>
<span data-ttu-id="d2e95-129">Ring0 Preview では、次のシナリオがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d2e95-129">The following scenarios are supported during Ring0 Preview.</span></span> 

### <a name="firewall-reporting-in-security-center"></a><span data-ttu-id="d2e95-130">セキュリティ センターでのファイアウォールレポート</span><span class="sxs-lookup"><span data-stu-id="d2e95-130">Firewall reporting in security center</span></span>

<span data-ttu-id="d2e95-131">ファイアウォール レポート ページの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d2e95-131">Here is a couple of examples of the firewall report pages.</span></span> <span data-ttu-id="d2e95-132">ここでは、受信、送信、およびアプリケーションアクティビティの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="d2e95-132">Here you will find a summary of inbound, outbound, and application activity.</span></span> <span data-ttu-id="d2e95-133">に移動すると、このページに直接アクセスできます https://security.microsoft.com/firewall 。</span><span class="sxs-lookup"><span data-stu-id="d2e95-133">You can access this page directly by going to https://security.microsoft.com/firewall.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d2e95-134">![[ホスト ファイアウォールのレポート] ページ](\images\host-firewall-reporting-page.png)</span><span class="sxs-lookup"><span data-stu-id="d2e95-134">![Host firewall reporting page](\images\host-firewall-reporting-page.png)</span></span>

<span data-ttu-id="d2e95-135">これらのレポートには、ファイアウォールブロックされた受信接続カードの下部にある [セキュリティ レポート デバイスのレポート] (セクション) にアクセス  >    >  することもできます。 </span><span class="sxs-lookup"><span data-stu-id="d2e95-135">These reports can also be accessed by going to **Reports** > **Security Report** > **Devices** (section) located at the bottom of the **Firewall Blocked Inbound Connections** card.</span></span>

### <a name="from-computers-with-a-blocked-connection-to-device"></a><span data-ttu-id="d2e95-136">"接続がブロックされているコンピューター" からデバイスへ</span><span class="sxs-lookup"><span data-stu-id="d2e95-136">From "Computers with a blocked connection" to device</span></span>

<span data-ttu-id="d2e95-137">カードは対話型オブジェクトをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d2e95-137">Cards support interactive objects.</span></span> <span data-ttu-id="d2e95-138">新しいタブで起動するデバイス名をクリックして、デバイスのアクティビティをドリル インし、[デバイス タイムライン] タブ https://securitycenter.microsoft.com **に直接移動** できます。</span><span class="sxs-lookup"><span data-stu-id="d2e95-138">You can drill into the activity of a device by clicking on the device name, which will launch https://securitycenter.microsoft.com in a new tab, and take you directly to the **Device Timeline** tab.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d2e95-139">![接続がブロックされているコンピューター](\images\firewall-reporting-blocked-connection.png)</span><span class="sxs-lookup"><span data-stu-id="d2e95-139">![Computers with a blocked connection](\images\firewall-reporting-blocked-connection.png)</span></span>

<span data-ttu-id="d2e95-140">[タイムライン] タブ **を選択** すると、そのデバイスに関連付けられたイベントの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2e95-140">You can now select the **Timeline** tab, which will give you a list of events associated with that device.</span></span> 

<span data-ttu-id="d2e95-141">表示ウィンドウの右上隅にある **[フィルター** ] ボタンをクリックした後、目的のイベントの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2e95-141">After clicking on the **Filters** button on the upper right-hand corner of the viewing pane, select the type of event you want.</span></span> <span data-ttu-id="d2e95-142">この場合、[ファイアウォール イベント] **を選択** すると、ウィンドウはファイアウォール イベントにフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="d2e95-142">In this case, select **Firewall events** and the pane will be filtered to Firewall events.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d2e95-143">![[フィルター] ボタン](\images\firewall-reporting-filters-button.png)</span><span class="sxs-lookup"><span data-stu-id="d2e95-143">![Filters button](\images\firewall-reporting-filters-button.png)</span></span>

### <a name="drill-into-advanced-hunting-preview-refresh"></a><span data-ttu-id="d2e95-144">高度な検索 (プレビュー更新) の詳細を確認する</span><span class="sxs-lookup"><span data-stu-id="d2e95-144">Drill into advanced hunting (preview refresh)</span></span>

<span data-ttu-id="d2e95-145">ファイアウォール レポートでは、[高度な検索を開く] ボタンをクリックして、カードから高度なハンティングに直接 **ドリルを実行** できます。</span><span class="sxs-lookup"><span data-stu-id="d2e95-145">Firewall reports support drilling from the card directly into **Advanced Hunting** by clicking the **Open Advanced hunting** button.</span></span> <span data-ttu-id="d2e95-146">クエリは事前に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d2e95-146">The query will be pre-populated.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d2e95-147">![高度な検索ボタンを開く](\images\firewall-reporting-advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="d2e95-147">![Open Advanced hunting button](\images\firewall-reporting-advanced-hunting.png)</span></span>

<span data-ttu-id="d2e95-148">クエリを実行し、過去 30 日間のすべての関連ファイアウォール イベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d2e95-148">The query can now be executed, and all related Firewall events from the last 30 days can be explored.</span></span> 

<span data-ttu-id="d2e95-149">追加のレポート、またはカスタムの変更については、クエリをレポートにエクスポートしてPower BI分析できます。</span><span class="sxs-lookup"><span data-stu-id="d2e95-149">For additional reporting, or custom changes, the query can be exported into Power BI for further analysis.</span></span> <span data-ttu-id="d2e95-150">カスタム レポートは、カスタム レポート[](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)スクリプトをダウンロードして、カスタム レポート を使用してWindows Defender ファイアウォールアクティビティをPower BI。</span><span class="sxs-lookup"><span data-stu-id="d2e95-150">Custom reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 

 