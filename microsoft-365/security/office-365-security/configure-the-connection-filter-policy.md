---
title: 既定の接続フィルターポリシーを構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) で、電子メールサーバーからのメールを許可またはブロックするように接続フィルターを構成する方法について説明します。
ms.openlocfilehash: 9b4f203f11e72b4459c9fa35d3e4fdca544cffbb
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209585"
---
# <a name="configure-connection-filtering"></a><span data-ttu-id="2dea3-103">接続フィルターの構成</span><span class="sxs-lookup"><span data-stu-id="2dea3-103">Configure connection filtering</span></span>

<span data-ttu-id="2dea3-104">Exchange Online または exchange online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 顧客のメールボックスを使用している Microsoft 365 顧客の場合は、EOP (特に既定の接続フィルターポリシー) で接続フィルターを使用して、適切なまたは不良なソース電子メールサーバーを IP アドレスで識別します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-104">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, you use connection filtering in EOP (specifically, the default connection filter policy) to identify good or bad source email servers by their IP addresses.</span></span> <span data-ttu-id="2dea3-105">既定の接続フィルターポリシーの主要なコンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2dea3-105">The key components of the default connection filter policy are:</span></span>

- <span data-ttu-id="2dea3-106">**Ip 許可一覧**: ip アドレスまたは ip アドレス範囲で指定した送信元電子メールサーバーからのすべての受信メッセージに対して、スパムフィルター処理をスキップします。</span><span class="sxs-lookup"><span data-stu-id="2dea3-106">**IP Allow List**: Skip spam filtering for for all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="2dea3-107">このようなソースからのメッセージにスパムフィルター処理が依然として発生する可能性があるシナリオについては、このトピックで後述する「 [IP 許可一覧のソースからのメッセージのフィルター処理](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dea3-107">For scenarios where spam filtering might still occur on messages from these sources, see the [Scenarios where messages from sources in the IP Allow List are still filtered](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) section later in this topic.</span></span> <span data-ttu-id="2dea3-108">IP 許可一覧が安全な送信者戦略全体にどのように適合するかの詳細については、「 [EOP での安全な送信者リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dea3-108">For more information about how the IP Allow List should fit into your overall safe senders strategy, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="2dea3-109">**Ip 禁止一覧**: ip アドレスまたは ip アドレス範囲で指定した送信元電子メールサーバーからのすべての受信メッセージをブロックします。</span><span class="sxs-lookup"><span data-stu-id="2dea3-109">**IP Block List**: Block all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="2dea3-110">受信メッセージは拒否され、スパムとしてマークされないため、追加のフィルター処理は行われません。IP 禁止一覧がブロックされる送信者の全体的な戦略にどのように適合するかの詳細については、「 [Create Block sender lists IN EOP](create-block-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dea3-110">The incoming messages are rejected, are not marked as spam, and no additional filtering occurs .For more information about how the IP Block List should fit into your overall blocked senders strategy, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="2dea3-111">**セーフリスト**:*セーフリスト*は、お客様の構成を必要としない、Microsoft データセンターの動的な許可一覧です。</span><span class="sxs-lookup"><span data-stu-id="2dea3-111">**Safe list**: The *safe list* is a dynamic allow list in the Microsoft datacenter that requires no customer configuration.</span></span> <span data-ttu-id="2dea3-112">Microsoft では、これらの信頼できる電子メールソースを、さまざまなサードパーティリストに対するサブスクリプションから識別しています。</span><span class="sxs-lookup"><span data-stu-id="2dea3-112">Microsoft identifies these trusted email sources from subscriptions to various third-party lists.</span></span> <span data-ttu-id="2dea3-113">セーフリストの使用を有効または無効にします。送信元の電子メールサーバーをセーフリストで構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="2dea3-113">You enable or disable the use of the safe list; you can't configure the source email servers on the safe list.</span></span> <span data-ttu-id="2dea3-114">セーフリスト上の電子メールサーバーからの受信メッセージに対して、スパムフィルター処理がスキップされます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-114">Spam filtering is skipped on incoming messages from the email servers on the safe list.</span></span>

<span data-ttu-id="2dea3-115">このトピックでは、セキュリティ & コンプライアンスセンターまたは PowerShell (exchange online のメールボックスを使用する Microsoft 365 組織の場合は exchange online PowerShell、exchange online メールボックスがない組織の場合は、スタンドアロン EOP PowerShell) で既定の接続フィルターポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-115">This topic describes how to configure the default connection filter policy in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span> <span data-ttu-id="2dea3-116">EOP での接続フィルターの使用方法については、「スパム対策[保護](anti-spam-protection.md)を参照する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dea3-116">For more information about how EOP uses connection filtering is part of your organization's overall anti-spam settings, see see [Anti-spam protection](anti-spam-protection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2dea3-117">IP 許可一覧、セーフリスト、および IP 禁止一覧は、組織内の電子メールを許可またはブロックするための全体的な戦略の一部です。</span><span class="sxs-lookup"><span data-stu-id="2dea3-117">The IP Allow List, safe list, and the IP Block List are one part of your overall strategy to allow or block email in your organization.</span></span> <span data-ttu-id="2dea3-118">詳細については、「[差出人セーフリストを作成する](create-safe-sender-lists-in-office-365.md)」および「[ブロックする送信者リストを作成する](create-block-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dea3-118">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md) and [Create blocked sender lists](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2dea3-119">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="2dea3-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2dea3-120"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2dea3-121">**[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-121">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="2dea3-122">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dea3-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2dea3-123">スタンドアロンの Exchange Online Protection PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dea3-123">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2dea3-124">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dea3-124">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="2dea3-125">既定の接続フィルターポリシーを変更するには、**組織の管理**または**セキュリティ管理者**の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dea3-125">To modify the default connection filter policy, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="2dea3-126">既定の接続フィルターポリシーに対する読み取り専用アクセスの場合は、**セキュリティリーダー**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dea3-126">For read-only access to the default connection filter policy, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="2dea3-127">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2dea3-127">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="2dea3-128">許可またはブロックする電子メールサーバー (送信者) の送信元 IP アドレスを確認するには、メッセージヘッダーの [接続 IP (**CIP**)] ヘッダーフィールドを確認します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-128">To find the source IP addresses of the email servers (senders) that you want to allow or block, you can check the connecting IP (**CIP**) header field in the message header.</span></span> <span data-ttu-id="2dea3-129">さまざまな電子メールクライアントのメッセージヘッダーを表示するには、「 [Outlook でインターネットメッセージヘッダーを表示](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dea3-129">To view a message header in various email clients, see [View internet message headers in Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

- <span data-ttu-id="2dea3-130">IP 許可一覧は、IP 禁止一覧より優先されます (両方のリストのアドレスがブロックされることはありません)。</span><span class="sxs-lookup"><span data-stu-id="2dea3-130">The IP Allow List takes precedence over the IP Block List (an address on both lists is not blocked).</span></span>

- <span data-ttu-id="2dea3-131">IP 許可一覧と IP 禁止一覧には、最大で1273エントリがサポートされています。これは、1つの IP アドレス、IP アドレスの範囲、またはクラスレスドメイン間ルーティング (CIDR) IP です。</span><span class="sxs-lookup"><span data-stu-id="2dea3-131">The IP Allow List and the IP Block List each support a maximum of 1273 entries, where an entry is a single IP address, an IP address range, or a Classless InterDomain Routing (CIDR) IP.</span></span>

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="2dea3-132">セキュリティ & コンプライアンスセンターを使用して既定の接続フィルターポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="2dea3-132">Use the Security & Compliance Center to modify the default connection filter policy</span></span>

1. <span data-ttu-id="2dea3-133">[セキュリティ & コンプライアンスセンター] で、[**脅威管理**ポリシーのスパム対策] に移動し \> **Policy** \> **Anti-Spam**ます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-133">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="2dea3-134">[**スパム対策設定**] ページで、[展開] アイコンをクリックして [**接続フィルターポリシー** ] を展開し、 ![ ](../../media/scc-expand-icon.png) [**ポリシーの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dea3-134">On the **Anti-spam settings** page, expand **Connection filter policy** by clicking ![Expand icon](../../media/scc-expand-icon.png), and then click **Edit policy**.</span></span>

3. <span data-ttu-id="2dea3-135">表示される**既定**のポップアップで、次のいずれかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-135">In the **Default** flyout that appears, configure any of the following settings:</span></span>

   - <span data-ttu-id="2dea3-136">**説明**: オプションで説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-136">**Description**: Enter optional descriptive text.</span></span>

   - <span data-ttu-id="2dea3-137">**IP 許可一覧**: [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dea3-137">**IP Allow List**: Click **Edit**.</span></span> <span data-ttu-id="2dea3-138">表示された**IP 許可一覧**のポップアップで、次の構文を使用して、[**アドレスまたはアドレスの範囲**] ボックスに IPV4 アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-138">In the **IP Allow List** flyout that appears, enter an IPV4 address in the **Address or address range** box using the following syntax:</span></span>

     - <span data-ttu-id="2dea3-139">単一の IP: たとえば、192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="2dea3-139">Single IP: For example, 192.168.1.1.</span></span>

     - <span data-ttu-id="2dea3-140">IP 範囲: たとえば、192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="2dea3-140">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

     - <span data-ttu-id="2dea3-141">CIDR IP: たとえば、192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="2dea3-141">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="2dea3-142">有効なネットワークマスク値は、/24 ~ 32 です。</span><span class="sxs-lookup"><span data-stu-id="2dea3-142">Valid network mask values are /24 through /32.</span></span> <span data-ttu-id="2dea3-143">CIDR IP マスク値/1 から/23 へのスパムフィルター処理をスキップするには、このトピックで後述する「[使用可能な範囲外の CIDR ip のスパムフィルタリングをスキップ](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dea3-143">To skip spam filtering for CIDR IP mask values /1 to /23, see the [Skip spam filtering for a CIDR IP outside of the available range](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) section later in this topic.</span></span>

     <span data-ttu-id="2dea3-144">IP アドレスまたはアドレスの範囲を追加するには、[追加] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-AddIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-144">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="2dea3-145">エントリを削除するには、[**許可された IP アドレス**] でエントリを選択し、 **[削除] をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-145">To remove an entry, select the entry in **Allowed IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="2dea3-146">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dea3-146">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="2dea3-147">**IP 禁止一覧**: [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dea3-147">**IP Block List**: Click **Edit**.</span></span> <span data-ttu-id="2dea3-148">表示される**Ip 禁止一覧**のポップアップで、Ip**許可一覧**の設定で前述したように、[**アドレスまたはアドレスの範囲**] ボックスに1つの ip、IP 範囲、または CIDR IP を入力します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-148">In the **IP Block List** flyout that appears, enter a single IP, IP range, or CIDR IP in the **Address or address range** box as previously described in the **IP Allow List** setting.</span></span>

     <span data-ttu-id="2dea3-149">IP アドレスまたはアドレスの範囲を追加するには、[追加] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-AddIcon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-149">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="2dea3-150">エントリを削除するには、[**ブロックする IP アドレス**] のエントリを選択し、 **[削除] をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-150">To remove an entry, select the entry in **Blocked IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="2dea3-151">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dea3-151">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="2dea3-152">**セーフ**リストを有効にする: セーフリストの使用を有効または無効にして、スパムフィルターをスキップする既知の良好な送信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-152">**Turn on safe list**: Enable or disable the use of the safe list to identify known, good senders that will skip spam filtering.</span></span>

4. <span data-ttu-id="2dea3-153">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dea3-153">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a><span data-ttu-id="2dea3-154">セキュリティ & コンプライアンスセンターを使用して既定の接続フィルターポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="2dea3-154">Use the Security & Compliance Center to view the default connection filter policy</span></span>

1. <span data-ttu-id="2dea3-155">[セキュリティ & コンプライアンスセンター] で、[**脅威管理**ポリシーのスパム対策] に移動し \> **Policy** \> **Anti-Spam**ます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-155">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="2dea3-156">[**スパム対策設定**] ページで、[**接続フィルターポリシー**] という名前の既定のポリシーの横にあるドロップダウンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dea3-156">On the **Anti-spam settings** page, click the drop down next to the default policy named **Connection filter policy**.</span></span>

3. <span data-ttu-id="2dea3-157">ポリシー設定が、表示されるドロップダウンに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-157">The policy settings are displayed in the drop down that opens.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="2dea3-158">Exchange Online PowerShell またはスタンドアロンの Exchange Online Protection PowerShell を使用して既定の接続フィルターポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="2dea3-158">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to modify the default connection filter policy</span></span>

<span data-ttu-id="2dea3-159">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="2dea3-159">Use the following syntax:</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

<span data-ttu-id="2dea3-160">**注**:</span><span class="sxs-lookup"><span data-stu-id="2dea3-160">**Notes**:</span></span>

- <span data-ttu-id="2dea3-161">有効な IP アドレスまたはアドレス範囲の値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2dea3-161">Valid IP address or address range values are:</span></span>

  - <span data-ttu-id="2dea3-162">単一の IP: たとえば、192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="2dea3-162">Single IP: For example, 192.168.1.1.</span></span>

  - <span data-ttu-id="2dea3-163">IP 範囲: たとえば、192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="2dea3-163">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

  - <span data-ttu-id="2dea3-164">CIDR IP: たとえば、192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="2dea3-164">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="2dea3-165">有効なネットワークマスク値は、/24 ~ 32 です。</span><span class="sxs-lookup"><span data-stu-id="2dea3-165">Valid network mask values are /24 through /32.</span></span>

- <span data-ttu-id="2dea3-166">既存のエントリを指定した値で*上書き*するには、次の構文を使用し `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` ます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-166">To *overwrite* any existing entries with the values you specify, use the following syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`.</span></span>

- <span data-ttu-id="2dea3-167">他の既存のエントリに影響を及ぼさずに、IP アドレスまたはアドレス範囲を*追加または削除*するには、次の構文を使用し `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` ます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-167">To *add or remove* IP addresses or address ranges without affecting other existing entries, use the following syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`.</span></span>

- <span data-ttu-id="2dea3-168">IP 許可一覧または IP 禁止一覧を空にするには、値を使用し `$null` ます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-168">To empty the IP Allow List or IP Block List, use the value `$null`.</span></span>

<span data-ttu-id="2dea3-169">この例では、指定した IP アドレスとアドレス範囲を使用して ip 許可一覧と IP 禁止一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-169">This example configures the IP Allow List and the IP Block List with the specified IP addresses and address ranges.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

<span data-ttu-id="2dea3-170">この例では、指定された IP アドレスとアドレス範囲を IP 許可一覧から追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-170">This example adds and removes the specified IP addresses and address ranges from the IP Allow List.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

<span data-ttu-id="2dea3-171">構文およびパラメーターの詳細については、「 [remove-hostedconnectionfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedconnectionfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dea3-171">For detailed syntax and parameter information, see [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedconnectionfilterpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2dea3-172">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="2dea3-172">How do you know this worked?</span></span>

<span data-ttu-id="2dea3-173">既定の接続フィルターポリシーが正常に変更されたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-173">To verify that you've successfully modified the default connection filter policy, do any of the following steps:</span></span>

- <span data-ttu-id="2dea3-174">[セキュリティ & コンプライアンスセンター] で、[**脅威管理**ポリシーのスパム対策] に移動し \> **Policy** \> **Anti-Spam** \> て、[**接続フィルターポリシー (always ON**)] の横にあるドロップダウンをクリックし、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-Spam** \> click the drop down next to **Connection filter policy (always ON**), and verify the settings.</span></span>

- <span data-ttu-id="2dea3-175">Exchange Online PowerShell またはスタンドアロンの Exchange Online Protection の PowerShell で、次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-175">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- <span data-ttu-id="2dea3-176">IP 許可一覧のエントリからテストメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-176">Send a test message from an entry on the IP Allow List.</span></span>

## <a name="additional-considerations-for-the-ip-allow-list"></a><span data-ttu-id="2dea3-177">IP 許可一覧に関するその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="2dea3-177">Additional considerations for the IP Allow List</span></span>

<span data-ttu-id="2dea3-178">次のセクションでは、IP 許可一覧を構成する際に知っておく必要があるその他の項目について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-178">The following sections identify additional items that you need to know about when you configure the IP Allow List.</span></span>

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a><span data-ttu-id="2dea3-179">使用可能な範囲外の CIDR IP のスパムフィルタリングをスキップする</span><span class="sxs-lookup"><span data-stu-id="2dea3-179">Skip spam filtering for a CIDR IP outside of the available range</span></span>

<span data-ttu-id="2dea3-180">このトピックの前半で説明したように、IP 許可一覧では、ネットワークマスク/24 ~ 32 の CIDR IP のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-180">As described earlier in this topic, you can only use a CIDR IP with the network mask /24 to /32 in the IP Allow List.</span></span> <span data-ttu-id="2dea3-181">/1 から/23 の範囲のソース電子メールサーバーからのメッセージに対するスパムフィルター処理をスキップするには、Exchange メールフロールール (トランスポートルールとも呼ばれる) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dea3-181">To skip spam filtering on messages from source email servers in the /1 to /23 range, you need to use Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="2dea3-182">ただし、Microsoft の専用またはサードパーティのブロックリストのいずれかに、[/1 ~ 23 CIDR IP] 範囲の IP アドレスが表示される場合は、メッセージがブロックされるため、この操作は可能な限り行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2dea3-182">But, we recommend that you don't do this if at all possible, because the messages will be blocked if an IP address in the /1 to /23 CIDR IP range appears on any of Microsoft's proprietary or third-party block lists.</span></span>

<span data-ttu-id="2dea3-183">潜在的な問題について十分に理解できたので、以下の設定を使用してメールフロールールを作成し、これらの IP アドレスからのメッセージがスパムフィルタリングをスキップするようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-183">Now that you're fully aware of the potential issues, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from these IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="2dea3-184">ルールの条件**Apply this rule if** : \> **送信者**の \> **ip アドレスがこれらのいずれかの範囲内にある場合、または完全に一致する**場合は、このルールを適用 \> します (/1 ~ 23 のネットワークマスクで CIDR ip を入力します)。</span><span class="sxs-lookup"><span data-stu-id="2dea3-184">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (enter your CIDR IP with a /1 to /23 network mask).</span></span>

- <span data-ttu-id="2dea3-185">ルールの処理:**メッセージのプロパティを変更する** \> **スパム信頼レベル (SCL) を設定**する \> **スパムフィルターをバイパス**する。</span><span class="sxs-lookup"><span data-stu-id="2dea3-185">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

<span data-ttu-id="2dea3-186">ルールを監査したり、ルールをテストしたり、特定の期間にルールをアクティブ化したり、その他の選択を行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-186">You can audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="2dea3-187">ルールを施行する前に一定期間ルールをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2dea3-187">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="2dea3-188">詳細については、「 [Exchange Online でメールフロールールを管理](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dea3-188">For more information, see [Manage mail flow rules in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span>

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a><span data-ttu-id="2dea3-189">同じソースから選択したメールドメインでスパムフィルター処理をスキップする</span><span class="sxs-lookup"><span data-stu-id="2dea3-189">Skip spam filtering on selective email domains from the same source</span></span>

<span data-ttu-id="2dea3-190">通常、ip アドレスまたはアドレス範囲を IP 許可一覧に追加すると、その電子メールソースからのすべての受信メッセージが信頼できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2dea3-190">Typically, adding an IP address or address range to the IP Allow List means you trust all incoming messages from that email source.</span></span> <span data-ttu-id="2dea3-191">しかし、送信元が複数のドメインからメールを送信している場合に、それらのドメインの一部に対してスパムフィルター処理をスキップする必要がある場合はどうすればよいでしょうか。</span><span class="sxs-lookup"><span data-stu-id="2dea3-191">But what if that source sends email from multiple domains, and you want to skip spam filtering for some of those domains, but not others?</span></span> <span data-ttu-id="2dea3-192">IP 許可一覧のみを使用してこれを行うことはできませんが、IP 許可一覧はメールフロールールと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-192">You can't use the IP Allow List alone to do this, but you can use the IP Allow List in combination with a mail flow rule.</span></span>

<span data-ttu-id="2dea3-193">たとえば、ソースメールサーバー192.168.1.25 は、ドメイン contoso.com、fabrikam.com、および tailspintoys.com から電子メールを送信しますが、fabrikam.com の送信者からのメッセージに対してのみスパムフィルターをスキップしたいとします。</span><span class="sxs-lookup"><span data-stu-id="2dea3-193">For example, the source email server 192.168.1.25 sends email from the domains contoso.com, fabrikam.com, and tailspintoys.com, but you only want to skip spam filtering for messages from senders in fabrikam.com.</span></span> <span data-ttu-id="2dea3-194">これを行うには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-194">To do this, use the following steps:</span></span>

1. <span data-ttu-id="2dea3-195">192.168.1.25 を IP 許可一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-195">Add 192.168.1.25 to the IP Allow List.</span></span>

2. <span data-ttu-id="2dea3-196">少なくとも次の設定を使用してメールフロールールを構成します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-196">Configure a mail flow rule with the following settings (at a minimum):</span></span>

   - <span data-ttu-id="2dea3-197">ルールの条件**Apply this rule if** : \> **送信者**の \> **IP アドレスがこれらのいずれかの範囲内にある場合、または** \> 192.168.1.25 (前の手順で ip 許可一覧に追加したものと同じ ip アドレスまたはアドレスの範囲) に正確に一致する場合は、このルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-197">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (the same IP address or address range that you added to the IP Allow List in the previous step).</span></span>

   - <span data-ttu-id="2dea3-198">ルールの処理:**メッセージのプロパティを変更する** \> **スパム信頼レベル (SCL)** \> **0**を設定します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-198">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **0**.</span></span>

   - <span data-ttu-id="2dea3-199">ルールの例外:**送信者** \> **ドメインは** \> fabrikam.com です (スパムフィルターをスキップするドメインのみ)。</span><span class="sxs-lookup"><span data-stu-id="2dea3-199">Rule exception: **The sender** \> **domain is** \> fabrikam.com (only the domain or domains that you want to skip spam filtering).</span></span>

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a><span data-ttu-id="2dea3-200">IP 許可一覧のソースからのメッセージが引き続きフィルター処理されるシナリオ</span><span class="sxs-lookup"><span data-stu-id="2dea3-200">Scenarios where messages from sources in the IP Allow List are still filtered</span></span>

<span data-ttu-id="2dea3-201">IP 許可一覧内の電子メールサーバーからのメッセージは、次のシナリオでは依然としてスパムフィルター処理の対象となります。</span><span class="sxs-lookup"><span data-stu-id="2dea3-201">Messages from an email server in your IP Allow List are still subject to spam filtering in the following scenarios:</span></span>

- <span data-ttu-id="2dea3-202">IP 許可一覧の ip アドレスは、Microsoft 365 の*任意*のテナントのオンプレミスの ip ベースの受信コネクタにも構成されています (このテナントを呼び出すことができます) **。また、** 最初にメッセージが検出された EOP サーバーが、microsoft データセンター内の*同じ*Active Directory フォレストに存在することになります。</span><span class="sxs-lookup"><span data-stu-id="2dea3-202">An IP address in your IP Allow List is also configured in an on-premises, IP-based inbound connector in *any* tenant in Microsoft 365 (let's call this Tenant A), **and** Tenant A and the EOP server that first encounters the message both happen to be in *the same* Active Directory forest in the Microsoft datacenters.</span></span> <span data-ttu-id="2dea3-203">このシナリオでは、 **Ipv: CAL** *が*メッセージの[スパム対策メッセージヘッダー](anti-spam-message-headers.md)に追加されます (メッセージがスパムフィルタリングをバイパスしていることを示します)。ただし、メッセージはスパムフィルター処理の対象となります。</span><span class="sxs-lookup"><span data-stu-id="2dea3-203">In this scenario, **IPV:CAL** *is* added to the message's [anti-spam message headers](anti-spam-message-headers.md) (indicating the message bypassed spam filtering), but the message is still subject to spam filtering.</span></span>

- <span data-ttu-id="2dea3-204">IP 許可一覧を含むテナントと、最初にメッセージを検出した EOP サーバーの両方が、Microsoft データセンター内の*異なる*Active Directory フォレストに存在する。</span><span class="sxs-lookup"><span data-stu-id="2dea3-204">Your tenant that contains the IP Allow List and the EOP server that first encounters the message both happen to be in *different* Active Directory forests in the Microsoft datacenters.</span></span> <span data-ttu-id="2dea3-205">このシナリオでは、 **Ipv: CAL** *は*メッセージヘッダーに追加されないため、メッセージはスパムフィルター処理の対象となります。</span><span class="sxs-lookup"><span data-stu-id="2dea3-205">In this scenario, **IPV:CAL** *is not* added to the message headers, so the message is still subject to spam filtering.</span></span>

<span data-ttu-id="2dea3-206">これらのシナリオのいずれかが発生した場合は、次の設定を使用してメールフロールールを作成することができます (最低限)。これにより、問題のある IP アドレスからのメッセージがスパムフィルター処理をスキップすることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-206">If you encounter either of these scenarios, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from the problematic IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="2dea3-207">ルールの条件**Apply this rule if** : \> **送信者の** \> **IP アドレスがこれらの範囲内にある場合、または完全に一致する**場合は \> (IP アドレスまたはアドレス)、このルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="2dea3-207">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (your IP address or addresses).</span></span>

- <span data-ttu-id="2dea3-208">ルールの処理:**メッセージのプロパティを変更する** \> **スパム信頼レベル (SCL) を設定**する \> **スパムフィルターをバイパス**する。</span><span class="sxs-lookup"><span data-stu-id="2dea3-208">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

## <a name="new-to-microsoft-365"></a><span data-ttu-id="2dea3-209">Microsoft 365 の新機能</span><span class="sxs-lookup"><span data-stu-id="2dea3-209">New to Microsoft 365?</span></span>

||
|:-----|
|<span data-ttu-id="2dea3-210">![LinkedIn Learning の短いアイコンは、 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365 に新しいものですか?**</span><span class="sxs-lookup"><span data-stu-id="2dea3-210">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="2dea3-211">LinkedIn ラーニングによって提供される**管理者と IT プロフェッショナル**向けの無料のビデオコースを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="2dea3-211">Discover free video courses for **Admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
