---
title: 既定の接続フィルター ポリシーを構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) で接続フィルターを構成して、電子メール サーバーからの電子メールを許可またはブロックする方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 43f6c1b9f3867670810f2c4e2ada13544d39380f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917060"
---
# <a name="configure-connection-filtering"></a><span data-ttu-id="aa936-103">接続フィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="aa936-103">Configure connection filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="aa936-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="aa936-104">**Applies to**</span></span>
- [<span data-ttu-id="aa936-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="aa936-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="aa936-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="aa936-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="aa936-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa936-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


<span data-ttu-id="aa936-108">Exchange Online のメールボックスを使用している Microsoft 365 のお客様、または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) のお客様の場合は、EOP (具体的には既定の接続フィルター ポリシー) で接続フィルターを使用して、IP アドレスによって適切または悪い送信元メール サーバーを識別します。</span><span class="sxs-lookup"><span data-stu-id="aa936-108">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, you use connection filtering in EOP (specifically, the default connection filter policy) to identify good or bad source email servers by their IP addresses.</span></span> <span data-ttu-id="aa936-109">既定の接続フィルター ポリシーの主な構成要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa936-109">The key components of the default connection filter policy are:</span></span>

- <span data-ttu-id="aa936-110">**IP 許可一覧**: IP アドレスまたは IP アドレス範囲で指定した送信元メール サーバーからの受信メッセージすべてについて、スパム フィルターをスキップします。</span><span class="sxs-lookup"><span data-stu-id="aa936-110">**IP Allow List**: Skip spam filtering for all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="aa936-111">これらのソースからのメッセージでスパム フィルター処理が引き続き発生する可能性があるシナリオについては、この記事の後半の [「IP](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 許可一覧のソースからのメッセージがフィルター処理されるシナリオ」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa936-111">For scenarios where spam filtering might still occur on messages from these sources, see the [Scenarios where messages from sources in the IP Allow List are still filtered](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) section later in this article.</span></span> <span data-ttu-id="aa936-112">IP 許可一覧が全体の差出人セーフ リスト戦略に適合する方法の詳細については、「EOP で差出人セーフ リストを作成する」 [を参照してください](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="aa936-112">For more information about how the IP Allow List should fit into your overall safe senders strategy, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="aa936-113">**IP ブロックリスト**: IP アドレスまたは IP アドレス範囲で指定した送信元メール サーバーからの受信メッセージをすべてブロックします。</span><span class="sxs-lookup"><span data-stu-id="aa936-113">**IP Block List**: Block all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="aa936-114">受信メッセージは拒否され、スパムとしてマークされ、追加のフィルター処理は行われません。</span><span class="sxs-lookup"><span data-stu-id="aa936-114">The incoming messages are rejected, are not marked as spam, and no additional filtering occurs.</span></span> <span data-ttu-id="aa936-115">IP ブロック 一覧を全体的にブロックする送信者戦略に適合する方法の詳細については、「EOP でブロック送信者リストを作成する」 [を参照してください](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="aa936-115">For more information about how the IP Block List should fit into your overall blocked senders strategy, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="aa936-116">**セーフ リスト**: セーフ *リストは* 、お客様の構成を必要とする Microsoft データセンターの動的な許可リストです。</span><span class="sxs-lookup"><span data-stu-id="aa936-116">**Safe list**: The *safe list* is a dynamic allow list in the Microsoft datacenter that requires no customer configuration.</span></span> <span data-ttu-id="aa936-117">Microsoft は、サブスクリプションからさまざまなサード パーティのリストへの信頼できる電子メール ソースを識別します。</span><span class="sxs-lookup"><span data-stu-id="aa936-117">Microsoft identifies these trusted email sources from subscriptions to various third-party lists.</span></span> <span data-ttu-id="aa936-118">セーフ リストの使用を有効または無効にします。セーフ リストでソース メール サーバーを構成できません。</span><span class="sxs-lookup"><span data-stu-id="aa936-118">You enable or disable the use of the safe list; you can't configure the source email servers on the safe list.</span></span> <span data-ttu-id="aa936-119">セーフ リスト上の電子メール サーバーからの受信メッセージでは、スパム フィルターはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="aa936-119">Spam filtering is skipped on incoming messages from the email servers on the safe list.</span></span>

<span data-ttu-id="aa936-120">このトピックでは、セキュリティ & コンプライアンス センターまたは PowerShell で既定の接続フィルター ポリシーを構成する方法について説明します (Exchange Online のメールボックスを持つ Microsoft 365 組織の Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell)。</span><span class="sxs-lookup"><span data-stu-id="aa936-120">This topic describes how to configure the default connection filter policy in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span> <span data-ttu-id="aa936-121">EOP が接続フィルターを使用する方法の詳細については、「スパム対策保護」を [参照してください](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="aa936-121">For more information about how EOP uses connection filtering is part of your organization's overall anti-spam settings, see see [Anti-spam protection](anti-spam-protection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="aa936-122">IP 許可一覧、セーフ リスト、および IP ブロック リストは、組織内の電子メールを許可またはブロックする全体的な戦略の 1 部です。</span><span class="sxs-lookup"><span data-stu-id="aa936-122">The IP Allow List, safe list, and the IP Block List are one part of your overall strategy to allow or block email in your organization.</span></span> <span data-ttu-id="aa936-123">詳細については、「差出人セーフ [リストの作成」および](create-safe-sender-lists-in-office-365.md) 「受信拒否 [リストの作成」を参照してください](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="aa936-123">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md) and [Create blocked sender lists](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="aa936-124">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="aa936-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="aa936-125"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="aa936-125">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="aa936-126">**[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa936-126">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="aa936-127">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa936-127">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="aa936-128">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa936-128">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="aa936-129">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa936-129">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="aa936-130">既定の接続フィルター ポリシーを変更するには、組織の管理役割グループまたはセキュリティ管理者役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa936-130">To modify the default connection filter policy, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="aa936-131">既定の接続フィルター ポリシーへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa936-131">For read-only access to the default connection filter policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="aa936-132">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa936-132">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="aa936-133">**注**:</span><span class="sxs-lookup"><span data-stu-id="aa936-133">**Notes**:</span></span>

  - <span data-ttu-id="aa936-134">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="aa936-134">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="aa936-135">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa936-135">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="aa936-136">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="aa936-136">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="aa936-137">許可またはブロックする電子メール サーバー (送信者) の送信元 IP アドレスを検索するには、メッセージ ヘッダーの接続 IP (**CIP**) ヘッダー フィールドを確認します。</span><span class="sxs-lookup"><span data-stu-id="aa936-137">To find the source IP addresses of the email servers (senders) that you want to allow or block, you can check the connecting IP (**CIP**) header field in the message header.</span></span> <span data-ttu-id="aa936-138">さまざまな電子メール クライアントでメッセージ ヘッダーを表示するには [、「Outlook でインターネット メッセージ ヘッダーを表示する」を参照してください](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)。</span><span class="sxs-lookup"><span data-stu-id="aa936-138">To view a message header in various email clients, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

- <span data-ttu-id="aa936-139">IP 許可一覧は IP ブロック リストよりも優先されます (両方のリストのアドレスはブロックされません)。</span><span class="sxs-lookup"><span data-stu-id="aa936-139">The IP Allow List takes precedence over the IP Block List (an address on both lists is not blocked).</span></span>

- <span data-ttu-id="aa936-140">IP 許可一覧と IP ブロック リストは、それぞれ最大 1273 エントリをサポートします。エントリは単一の IP アドレス、IP アドレス範囲、または Classless InterDomain Routing (CIDR) IP です。</span><span class="sxs-lookup"><span data-stu-id="aa936-140">The IP Allow List and the IP Block List each support a maximum of 1273 entries, where an entry is a single IP address, an IP address range, or a Classless InterDomain Routing (CIDR) IP.</span></span>

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="aa936-141">既定の接続&ポリシーを変更するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa936-141">Use the Security & Compliance Center to modify the default connection filter policy</span></span>

1. <span data-ttu-id="aa936-142">[セキュリティ & コンプライアンス センター] で、[脅威管理ポリシー **スパム** \>  \> **対策] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="aa936-142">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="aa936-143">[スパム対策 **の設定]** ページで、[展開] アイコンをクリックして [接続フィルター ポリシー] を展開し、[ポリシーの編集 ![ ] ](../../media/scc-expand-icon.png) **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="aa936-143">On the **Anti-spam settings** page, expand **Connection filter policy** by clicking ![Expand icon](../../media/scc-expand-icon.png), and then click **Edit policy**.</span></span>

3. <span data-ttu-id="aa936-144">表示される **既定の** フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="aa936-144">In the **Default** flyout that appears, configure any of the following settings:</span></span>

   - <span data-ttu-id="aa936-145">**説明**: 省略可能な説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="aa936-145">**Description**: Enter optional descriptive text.</span></span>

   - <span data-ttu-id="aa936-146">**IP 許可一覧**: [編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="aa936-146">**IP Allow List**: Click **Edit**.</span></span> <span data-ttu-id="aa936-147">表示される **IP 許可一覧** のフライアウトで、次の構文を使用して、[アドレスまたはアドレス範囲] ボックスに IPV4 アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="aa936-147">In the **IP Allow List** flyout that appears, enter an IPV4 address in the **Address or address range** box using the following syntax:</span></span>

     - <span data-ttu-id="aa936-148">単一 IP: たとえば、192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="aa936-148">Single IP: For example, 192.168.1.1.</span></span>

     - <span data-ttu-id="aa936-149">IP 範囲: たとえば、192.168.0.1-192.168.0.254 です。</span><span class="sxs-lookup"><span data-stu-id="aa936-149">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

     - <span data-ttu-id="aa936-150">CIDR IP: たとえば、192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="aa936-150">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="aa936-151">有効なネットワーク マスクの値は、/24 ~ /32 です。</span><span class="sxs-lookup"><span data-stu-id="aa936-151">Valid network mask values are /24 through /32.</span></span> <span data-ttu-id="aa936-152">CIDR IP マスク値 /1 ~ /23 のスパム フィルター処理をスキップするには、この記事の後半の「利用可能な範囲外の [CIDR IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) のスパム フィルターをスキップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa936-152">To skip spam filtering for CIDR IP mask values /1 to /23, see the [Skip spam filtering for a CIDR IP outside of the available range](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) section later in this article.</span></span>

     <span data-ttu-id="aa936-153">IP アドレスまたはアドレス範囲を追加するには、[アイコンの追加 **] を** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="aa936-153">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="aa936-154">エントリを削除するには、[許可された IP アドレス] でエントリを選択 **し、[** 削除] **をクリック** ![ します ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="aa936-154">To remove an entry, select the entry in **Allowed IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="aa936-155">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa936-155">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="aa936-156">**IP ブロック リスト**: [編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="aa936-156">**IP Block List**: Click **Edit**.</span></span> <span data-ttu-id="aa936-157">表示される **[IP ブロック一** 覧] フライアウトで、[IP 許可一覧] 設定で説明したように、[アドレスまたはアドレス範囲] ボックスに単一の **IP、IP** 範囲、または CIDR IP を入力します。</span><span class="sxs-lookup"><span data-stu-id="aa936-157">In the **IP Block List** flyout that appears, enter a single IP, IP range, or CIDR IP in the **Address or address range** box as previously described in the **IP Allow List** setting.</span></span>

     <span data-ttu-id="aa936-158">IP アドレスまたはアドレス範囲を追加するには、[アイコンの追加 **] を** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="aa936-158">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="aa936-159">エントリを削除するには、[ブロックされた IP アドレス] でエントリを選択 **し、[** 削除] **をクリック** ![ します ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="aa936-159">To remove an entry, select the entry in **Blocked IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="aa936-160">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa936-160">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="aa936-161">**セーフ リストを有効にする**: スパム フィルターをスキップする既知の優れた送信者を識別するために、セーフ リストの使用を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="aa936-161">**Turn on safe list**: Enable or disable the use of the safe list to identify known, good senders that will skip spam filtering.</span></span>

4. <span data-ttu-id="aa936-162">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa936-162">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a><span data-ttu-id="aa936-163">既定の接続&ポリシーを表示するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa936-163">Use the Security & Compliance Center to view the default connection filter policy</span></span>

1. <span data-ttu-id="aa936-164">[セキュリティ & コンプライアンス センター] で、[脅威管理ポリシー **スパム** \>  \> **対策] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="aa936-164">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="aa936-165">[スパム **対策の設定] ページ** で、[接続フィルター ポリシー] という名前の既定のポリシーの横にあるドロップダウン **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="aa936-165">On the **Anti-spam settings** page, click the drop down next to the default policy named **Connection filter policy**.</span></span>

3. <span data-ttu-id="aa936-166">開くドロップダウンにポリシー設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa936-166">The policy settings are displayed in the drop down that opens.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="aa936-167">Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して既定の接続フィルター ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="aa936-167">Use Exchange Online PowerShell or standalone EOP PowerShell to modify the default connection filter policy</span></span>

<span data-ttu-id="aa936-168">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="aa936-168">Use the following syntax:</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

<span data-ttu-id="aa936-169">**注**:</span><span class="sxs-lookup"><span data-stu-id="aa936-169">**Notes**:</span></span>

- <span data-ttu-id="aa936-170">有効な IP アドレスまたはアドレス範囲の値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa936-170">Valid IP address or address range values are:</span></span>

  - <span data-ttu-id="aa936-171">単一 IP: たとえば、192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="aa936-171">Single IP: For example, 192.168.1.1.</span></span>

  - <span data-ttu-id="aa936-172">IP 範囲: たとえば、192.168.0.1-192.168.0.254 です。</span><span class="sxs-lookup"><span data-stu-id="aa936-172">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

  - <span data-ttu-id="aa936-173">CIDR IP: たとえば、192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="aa936-173">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="aa936-174">有効なネットワーク マスクの値は、/24 ~ /32 です。</span><span class="sxs-lookup"><span data-stu-id="aa936-174">Valid network mask values are /24 through /32.</span></span>

- <span data-ttu-id="aa936-175">指定 *した* 値で既存のエントリを上書きするには、次の構文を使用します `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 。</span><span class="sxs-lookup"><span data-stu-id="aa936-175">To *overwrite* any existing entries with the values you specify, use the following syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`.</span></span>

- <span data-ttu-id="aa936-176">他 *の既存のエントリ* に影響を与えることなく IP アドレスまたはアドレス範囲を追加または削除するには、次の構文を使用します `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 。</span><span class="sxs-lookup"><span data-stu-id="aa936-176">To *add or remove* IP addresses or address ranges without affecting other existing entries, use the following syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`.</span></span>

- <span data-ttu-id="aa936-177">IP 許可一覧または IP ブロック 一覧を空にするには、値を使用します `$null` 。</span><span class="sxs-lookup"><span data-stu-id="aa936-177">To empty the IP Allow List or IP Block List, use the value `$null`.</span></span>

<span data-ttu-id="aa936-178">次の使用例は、IP 許可一覧と IP ブロック 一覧を、指定した IP アドレスとアドレス範囲で構成します。</span><span class="sxs-lookup"><span data-stu-id="aa936-178">This example configures the IP Allow List and the IP Block List with the specified IP addresses and address ranges.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

<span data-ttu-id="aa936-179">次の使用例は、指定した IP アドレスとアドレス範囲を IP 許可一覧から追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="aa936-179">This example adds and removes the specified IP addresses and address ranges from the IP Allow List.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

<span data-ttu-id="aa936-180">構文とパラメーターの詳細については [、「Set-HostedConnectionFilterPolicy」を参照してください](/powershell/module/exchange/set-hostedconnectionfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="aa936-180">For detailed syntax and parameter information, see [Set-HostedConnectionFilterPolicy](/powershell/module/exchange/set-hostedconnectionfilterpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="aa936-181">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="aa936-181">How do you know this worked?</span></span>

<span data-ttu-id="aa936-182">既定の接続フィルター ポリシーが正常に変更されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="aa936-182">To verify that you've successfully modified the default connection filter policy, do any of the following steps:</span></span>

- <span data-ttu-id="aa936-183">[セキュリティ & コンプライアンス センター] で、[脅威管理ポリシー] [スパム対策] に移動し、[接続フィルター ポリシー ] (常にオン) の横にあるドロップダウン をクリックし、 \>  \>  \> 設定を確認します。 </span><span class="sxs-lookup"><span data-stu-id="aa936-183">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-Spam** \> click the drop down next to **Connection filter policy (always ON**), and verify the settings.</span></span>

- <span data-ttu-id="aa936-184">Exchange Online PowerShell またはスタンドアロン EOP PowerShell で、次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="aa936-184">In Exchange Online PowerShell or standalone EOP PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- <span data-ttu-id="aa936-185">IP 許可一覧のエントリからテスト メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="aa936-185">Send a test message from an entry on the IP Allow List.</span></span>

## <a name="additional-considerations-for-the-ip-allow-list"></a><span data-ttu-id="aa936-186">IP 許可一覧に関するその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="aa936-186">Additional considerations for the IP Allow List</span></span>

<span data-ttu-id="aa936-187">次のセクションでは、IP 許可一覧を構成する際に知る必要があるその他の項目を特定します。</span><span class="sxs-lookup"><span data-stu-id="aa936-187">The following sections identify additional items that you need to know about when you configure the IP Allow List.</span></span>

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a><span data-ttu-id="aa936-188">利用可能な範囲外の CIDR IP のスパム フィルター処理をスキップする</span><span class="sxs-lookup"><span data-stu-id="aa936-188">Skip spam filtering for a CIDR IP outside of the available range</span></span>

<span data-ttu-id="aa936-189">この記事で前述したように、IP 許可一覧では、ネットワーク マスク /24 ~ /32 の CIDR IP のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="aa936-189">As described earlier in this article, you can only use a CIDR IP with the network mask /24 to /32 in the IP Allow List.</span></span> <span data-ttu-id="aa936-190">/1 ~ /23 範囲の送信元メール サーバーからのメッセージに対するスパム フィルターをスキップするには、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa936-190">To skip spam filtering on messages from source email servers in the /1 to /23 range, you need to use Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="aa936-191">ただし、/1 ~ /23 CIDR IP 範囲の IP アドレスが Microsoft の独自のブロック リストまたはサード パーティ製のブロック リストに表示される場合、メッセージはブロックされますので、可能な限りこれを行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="aa936-191">But, we recommend that you don't do this if at all possible, because the messages will be blocked if an IP address in the /1 to /23 CIDR IP range appears on any of Microsoft's proprietary or third-party block lists.</span></span>

<span data-ttu-id="aa936-192">潜在的な問題を十分に認識したので、(少なくとも) 次の設定でメール フロー ルールを作成して、これらの IP アドレスからのメッセージがスパム フィルター処理をスキップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa936-192">Now that you're fully aware of the potential issues, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from these IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="aa936-193">ルールの条件:**送信者** IP アドレスがこれらの範囲または完全に一致する場合は、このルールを適用します \>  \>  \> (/1 ~ /23 ネットワーク マスクを使用して CIDR IP を入力します)。</span><span class="sxs-lookup"><span data-stu-id="aa936-193">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (enter your CIDR IP with a /1 to /23 network mask).</span></span>

- <span data-ttu-id="aa936-194">ルール アクション: **メッセージのプロパティを変更** \> **する スパム信頼レベル (SCL)** \> **バイパス スパム フィルターを設定します**。</span><span class="sxs-lookup"><span data-stu-id="aa936-194">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

<span data-ttu-id="aa936-195">ルールの監査、ルールのテスト、特定の期間中のルールのアクティブ化、その他の選択を行います。</span><span class="sxs-lookup"><span data-stu-id="aa936-195">You can audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="aa936-196">ルールを施行する前に一定期間ルールをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aa936-196">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="aa936-197">詳細については [、「Exchange Online でメール フロー ルールを管理する」を参照してください](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="aa936-197">For more information, see [Manage mail flow rules in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span>

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a><span data-ttu-id="aa936-198">同じソースからの選択的なメール ドメインのスパム フィルターをスキップする</span><span class="sxs-lookup"><span data-stu-id="aa936-198">Skip spam filtering on selective email domains from the same source</span></span>

<span data-ttu-id="aa936-199">通常、IP 許可一覧に IP アドレスまたはアドレス範囲を追加すると、そのメール ソースからのすべての受信メッセージを信頼できます。</span><span class="sxs-lookup"><span data-stu-id="aa936-199">Typically, adding an IP address or address range to the IP Allow List means you trust all incoming messages from that email source.</span></span> <span data-ttu-id="aa936-200">しかし、そのソースが複数のドメインから電子メールを送信し、それらのドメインの一部に対するスパム フィルターをスキップするが、他のドメインには送信しない場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="aa936-200">But what if that source sends email from multiple domains, and you want to skip spam filtering for some of those domains, but not others?</span></span> <span data-ttu-id="aa936-201">IP 許可一覧を単独で使用することはできませんが、メール フロー ルールと組み合わせて IP 許可一覧を使用できます。</span><span class="sxs-lookup"><span data-stu-id="aa936-201">You can't use the IP Allow List alone to do this, but you can use the IP Allow List in combination with a mail flow rule.</span></span>

<span data-ttu-id="aa936-202">たとえば、送信元電子メール サーバー 192.168.1.25 は、ドメイン contoso.com、fabrikam.com、および tailspintoys.com から電子メールを送信しますが、fabrikam.com の送信者からのメッセージに対するスパム フィルター処理のみをスキップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa936-202">For example, the source email server 192.168.1.25 sends email from the domains contoso.com, fabrikam.com, and tailspintoys.com, but you only want to skip spam filtering for messages from senders in fabrikam.com.</span></span> <span data-ttu-id="aa936-203">これを行うには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa936-203">To do this, use the following steps:</span></span>

1. <span data-ttu-id="aa936-204">IP 許可一覧に 192.168.1.25 を追加します。</span><span class="sxs-lookup"><span data-stu-id="aa936-204">Add 192.168.1.25 to the IP Allow List.</span></span>

2. <span data-ttu-id="aa936-205">次の設定を使用してメール フロー ルールを構成します (少なくとも)。</span><span class="sxs-lookup"><span data-stu-id="aa936-205">Configure a mail flow rule with the following settings (at a minimum):</span></span>

   - <span data-ttu-id="aa936-206">ルール **の条件:** 送信者 IP アドレスがこれらの範囲にある場合、または \>  \>  \> 192.168.1.25 と完全に一致する場合は、このルールを適用します (前の手順で IP 許可一覧に追加したのと同じ IP アドレスまたはアドレス範囲)。</span><span class="sxs-lookup"><span data-stu-id="aa936-206">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (the same IP address or address range that you added to the IP Allow List in the previous step).</span></span>

   - <span data-ttu-id="aa936-207">ルールアクション: **メッセージのプロパティを変更** \> **する スパム信頼レベル (SCL)** \> **0 を設定します**。</span><span class="sxs-lookup"><span data-stu-id="aa936-207">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **0**.</span></span>

   - <span data-ttu-id="aa936-208">ルール例外:**送信者ドメイン** は fabrikam.com (スパム フィルターをスキップするドメインまたはドメイン \>  \> のみ) です。</span><span class="sxs-lookup"><span data-stu-id="aa936-208">Rule exception: **The sender** \> **domain is** \> fabrikam.com (only the domain or domains that you want to skip spam filtering).</span></span>

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a><span data-ttu-id="aa936-209">IP 許可一覧のソースからのメッセージがまだフィルター処理されるシナリオ</span><span class="sxs-lookup"><span data-stu-id="aa936-209">Scenarios where messages from sources in the IP Allow List are still filtered</span></span>

<span data-ttu-id="aa936-210">IP 許可一覧内の電子メール サーバーからのメッセージは、次のシナリオでスパム フィルター処理の対象になります。</span><span class="sxs-lookup"><span data-stu-id="aa936-210">Messages from an email server in your IP Allow List are still subject to spam filtering in the following scenarios:</span></span>

- <span data-ttu-id="aa936-211">IP 許可一覧の IP アドレスは、Microsoft 365 の任意のテナント内のオンプレミスの IP ベースの受信コネクタ (このテナント Aと呼ぶ)、および最初にメッセージを検出したテナント A と EOP サーバーで構成され、両方とも Microsoft データセンター内の同じ *Active* Directory フォレストに存在します。</span><span class="sxs-lookup"><span data-stu-id="aa936-211">An IP address in your IP Allow List is also configured in an on-premises, IP-based inbound connector in *any* tenant in Microsoft 365 (let's call this Tenant A), **and** Tenant A and the EOP server that first encounters the message both happen to be in *the same* Active Directory forest in the Microsoft datacenters.</span></span> <span data-ttu-id="aa936-212">このシナリオでは **、IPV:CAL** がメッセージのスパム対策メッセージ ヘッダー [(メッセージ](anti-spam-message-headers.md)によってバイパスされたスパム フィルターを示す) に追加されますが、メッセージはスパム フィルター処理の対象です。</span><span class="sxs-lookup"><span data-stu-id="aa936-212">In this scenario, **IPV:CAL** *is* added to the message's [anti-spam message headers](anti-spam-message-headers.md) (indicating the message bypassed spam filtering), but the message is still subject to spam filtering.</span></span>

- <span data-ttu-id="aa936-213">IP 許可一覧と、最初にメッセージが検出された EOP サーバーを含むテナントは、Microsoft データセンター内 *の異なる* Active Directory フォレストに存在します。</span><span class="sxs-lookup"><span data-stu-id="aa936-213">Your tenant that contains the IP Allow List and the EOP server that first encounters the message both happen to be in *different* Active Directory forests in the Microsoft datacenters.</span></span> <span data-ttu-id="aa936-214">このシナリオでは **、IPV:CAL** はメッセージ ヘッダーに追加されないので、メッセージはスパム フィルター処理の対象になります。</span><span class="sxs-lookup"><span data-stu-id="aa936-214">In this scenario, **IPV:CAL** *is not* added to the message headers, so the message is still subject to spam filtering.</span></span>

<span data-ttu-id="aa936-215">これらのシナリオのどちらかが発生した場合は、(少なくとも) 次の設定を使用してメール フロー ルールを作成して、問題のある IP アドレスからのメッセージがスパム フィルター処理をスキップします。</span><span class="sxs-lookup"><span data-stu-id="aa936-215">If you encounter either of these scenarios, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from the problematic IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="aa936-216">ルールの条件:**送信者** IP アドレスがこれらの範囲にある場合、または完全に一致する (IP アドレスまたはアドレス) 場合は、この \>  \>  \> ルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="aa936-216">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (your IP address or addresses).</span></span>

- <span data-ttu-id="aa936-217">ルール アクション: **メッセージのプロパティを変更** \> **する スパム信頼レベル (SCL)** \> **バイパス スパム フィルターを設定します**。</span><span class="sxs-lookup"><span data-stu-id="aa936-217">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

## <a name="new-to-microsoft-365"></a><span data-ttu-id="aa936-218">Microsoft 365 の新機能</span><span class="sxs-lookup"><span data-stu-id="aa936-218">New to Microsoft 365?</span></span>

****

<span data-ttu-id="aa936-219">![LinkedIn Learning New ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **to Microsoft 365** のショート アイコン</span><span class="sxs-lookup"><span data-stu-id="aa936-219">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="aa936-220">LinkedIn Learning が提供する **Microsoft 365** 管理者と IT プロ向け無料のビデオ コースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="aa936-220">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>