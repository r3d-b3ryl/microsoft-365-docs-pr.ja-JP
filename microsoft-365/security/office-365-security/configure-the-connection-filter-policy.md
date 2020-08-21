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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、電子メール サーバーからのメールを許可またはブロックするために、Exchange Online Protection (EOP) で接続フィルターを構成する方法について学習できます。
ms.openlocfilehash: 45213ff36c7efc76a83a2c520e0369211ffecf53
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827847"
---
# <a name="configure-connection-filtering"></a><span data-ttu-id="1bc06-103">接続フィルターの構成</span><span class="sxs-lookup"><span data-stu-id="1bc06-103">Configure connection filtering</span></span>

<span data-ttu-id="1bc06-104">Exchange Online のメールボックスを使用している Microsoft 365 のお客様、または Exchange Online のメールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) をお使いのお客様の場合は、EOP の接続フィルター (具体的には既定の接続フィルター ポリシー) を使用して、IP アドレスに基づいて良好なまたは不適切な送信元の電子メール サーバーを特定します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-104">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, you use connection filtering in EOP (specifically, the default connection filter policy) to identify good or bad source email servers by their IP addresses.</span></span> <span data-ttu-id="1bc06-105">既定の接続フィルター ポリシーの主な構成要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1bc06-105">The key components of the default connection filter policy are:</span></span>

- <span data-ttu-id="1bc06-106">**IP 許可一覧**: IP アドレスまたは IP アドレス範囲で指定した送信元の電子メール サーバーからのすべての受信メッセージに対して、スパム フィルターをスキップします。</span><span class="sxs-lookup"><span data-stu-id="1bc06-106">**IP Allow List**: Skip spam filtering for all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="1bc06-107">これらのソースからのメッセージにスパム フィルターが引き続き発生する可能性があるシナリオについては、このトピックの [後半にある「IP 許可](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 一覧のソースからのメッセージ」でフィルター処理が実行されるシナリオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bc06-107">For scenarios where spam filtering might still occur on messages from these sources, see the [Scenarios where messages from sources in the IP Allow List are still filtered](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) section later in this topic.</span></span> <span data-ttu-id="1bc06-108">IP 許可一覧を信頼できる差出人の全体的な戦略にどのようにして適用するかについては [、「EOP で信頼できる送信者リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="1bc06-108">For more information about how the IP Allow List should fit into your overall safe senders strategy, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="1bc06-109">**IP 禁止一覧**: IP アドレスまたは IP アドレス範囲で指定した送信元メール サーバーからの受信メッセージをすべてブロックする。</span><span class="sxs-lookup"><span data-stu-id="1bc06-109">**IP Block List**: Block all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="1bc06-110">受信メッセージは拒否され、スパムとしてマークされなく、追加のフィルター処理は行いません。</span><span class="sxs-lookup"><span data-stu-id="1bc06-110">The incoming messages are rejected, are not marked as spam, and no additional filtering occurs.</span></span> <span data-ttu-id="1bc06-111">受信拒否リスト全体に IP 禁止一覧を設定する方法の詳細については、「EOP で受信 [拒否リストを作成する」を参照してください](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="1bc06-111">For more information about how the IP Block List should fit into your overall blocked senders strategy, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="1bc06-112">**セーフ**リスト : セ *ーフ リスト* は、ユーザーによる設定が必要な Microsoft データセンター内の動的許可リストです。</span><span class="sxs-lookup"><span data-stu-id="1bc06-112">**Safe list**: The *safe list* is a dynamic allow list in the Microsoft datacenter that requires no customer configuration.</span></span> <span data-ttu-id="1bc06-113">Microsoft は、これらの信頼できるメール ソースをサブスクリプションからさまざまなサード パーティのリストに送信された形式で識別します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-113">Microsoft identifies these trusted email sources from subscriptions to various third-party lists.</span></span> <span data-ttu-id="1bc06-114">セーフ リストの使用を有効または無効にできます。セーフ リストの移行元の電子メール サーバーを構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="1bc06-114">You enable or disable the use of the safe list; you can't configure the source email servers on the safe list.</span></span> <span data-ttu-id="1bc06-115">スパム フィルターは、セーフ リスト上の電子メール サーバーからの受信メッセージにスキップされます。</span><span class="sxs-lookup"><span data-stu-id="1bc06-115">Spam filtering is skipped on incoming messages from the email servers on the safe list.</span></span>

<span data-ttu-id="1bc06-116">このトピックでは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online にメールボックスを持つ Microsoft 365 組織用の Exchange Online PowerShell;Exchange Online メールボックスを使用している組織用のスタンドアロン EOP PowerShell) を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-116">This topic describes how to configure the default connection filter policy in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span> <span data-ttu-id="1bc06-117">EOP で接続フィルターを使用する方法が組織の全体的なスパム対策設定に含まれますのかについては、「スパム対策保護 [」を参照してください](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="1bc06-117">For more information about how EOP uses connection filtering is part of your organization's overall anti-spam settings, see see [Anti-spam protection](anti-spam-protection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1bc06-118">IP 許可一覧、セーフ リスト、IP 禁止一覧は、組織内で電子メールを許可またはブロックする全体的な戦略の一部です。</span><span class="sxs-lookup"><span data-stu-id="1bc06-118">The IP Allow List, safe list, and the IP Block List are one part of your overall strategy to allow or block email in your organization.</span></span> <span data-ttu-id="1bc06-119">詳細については、「差出人セー[フ リストを作成する」および「ブロック](create-safe-sender-lists-in-office-365.md)[する差出人リストの作成」を参照してください](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="1bc06-119">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md) and [Create blocked sender lists](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1bc06-120">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="1bc06-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1bc06-121"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="1bc06-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1bc06-122">**[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-122">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="1bc06-123">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bc06-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1bc06-124">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bc06-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1bc06-125">このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bc06-125">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="1bc06-126">既定の接続フィルター ポリシーを変更するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bc06-126">To modify the default connection filter policy, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="1bc06-127">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="1bc06-127">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="1bc06-128">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="1bc06-128">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="1bc06-129">既定の接続フィルター ポリシーへの読み取り専用アクセスを行う場合は、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bc06-129">For read-only access to the default connection filter policy, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="1bc06-130">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="1bc06-130">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="1bc06-131">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="1bc06-131">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="1bc06-132">許可またはブロックする電子メール サーバーの送信元 IP アドレス (送信者) を見つけるには、メッセージ ヘッダー内の接続 IP **(CIP)** ヘッダー フィールドを確認します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-132">To find the source IP addresses of the email servers (senders) that you want to allow or block, you can check the connecting IP (**CIP**) header field in the message header.</span></span> <span data-ttu-id="1bc06-133">さまざまなメール クライアントでメッセージ ヘッダーを表示するには [、「Outlook でインターネット メッセージ ヘッダーを表示する」を参照してください](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)。</span><span class="sxs-lookup"><span data-stu-id="1bc06-133">To view a message header in various email clients, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

- <span data-ttu-id="1bc06-134">IP 許可一覧は IP 禁止一覧より優先されます (両方の一覧のアドレスはブロックされません)。</span><span class="sxs-lookup"><span data-stu-id="1bc06-134">The IP Allow List takes precedence over the IP Block List (an address on both lists is not blocked).</span></span>

- <span data-ttu-id="1bc06-135">IP 許可一覧と IP 禁止一覧は、最大 1,273 個のエントリをサポートします。エントリは、単一の IP アドレス、IP アドレス範囲、またはクラスレス ドメイン間ルーティング (CIDR) IP です。</span><span class="sxs-lookup"><span data-stu-id="1bc06-135">The IP Allow List and the IP Block List each support a maximum of 1273 entries, where an entry is a single IP address, an IP address range, or a Classless InterDomain Routing (CIDR) IP.</span></span>

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="1bc06-136">セキュリティ コンプライアンス センターを&、既定の接続フィルター ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="1bc06-136">Use the Security & Compliance Center to modify the default connection filter policy</span></span>

1. <span data-ttu-id="1bc06-137">セキュリティ コンプライアンス センター&、脅威管理**ポリシーの** \> **Policy** \> **スパム対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="1bc06-137">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="1bc06-138">[スパム対策 **の設定] ページで、[** 展開] アイコン **をクリックし、[ポリシーの** 編集] ![ を ](../../media/scc-expand-icon.png) クリックして、[接続フィルター ポリシー] を **展開します**。</span><span class="sxs-lookup"><span data-stu-id="1bc06-138">On the **Anti-spam settings** page, expand **Connection filter policy** by clicking ![Expand icon](../../media/scc-expand-icon.png), and then click **Edit policy**.</span></span>

3. <span data-ttu-id="1bc06-139">表示される **既定** のポップアップで、次のいずれかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-139">In the **Default** flyout that appears, configure any of the following settings:</span></span>

   - <span data-ttu-id="1bc06-140">**Description**: 説明テキストを入力します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="1bc06-140">**Description**: Enter optional descriptive text.</span></span>

   - <span data-ttu-id="1bc06-141">**IP 許可一覧**: [編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1bc06-141">**IP Allow List**: Click **Edit**.</span></span> <span data-ttu-id="1bc06-142">表示される **IP 許可一覧** のポップアップで、次の構文を使用してアドレスまたはアドレス **範囲ボックスに** IPV4 アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-142">In the **IP Allow List** flyout that appears, enter an IPV4 address in the **Address or address range** box using the following syntax:</span></span>

     - <span data-ttu-id="1bc06-143">単一の IP: 例: 192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="1bc06-143">Single IP: For example, 192.168.1.1.</span></span>

     - <span data-ttu-id="1bc06-144">IP 範囲: 例: 192.168.0.1 から 192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="1bc06-144">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

     - <span data-ttu-id="1bc06-145">CIDR IP:例: 192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="1bc06-145">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="1bc06-146">有効なネットワーク マスク値は /24 ~ /32 です。</span><span class="sxs-lookup"><span data-stu-id="1bc06-146">Valid network mask values are /24 through /32.</span></span> <span data-ttu-id="1bc06-147">CIDR IP マスク値 /1 ~ /23 のスパム フィルター処理をスキップするには、このトピックで後述する使用可能な範囲外の CIDR IP に対する [[Skip spam filtering] (CIDR IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) のスパム フィルターをスキップする) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bc06-147">To skip spam filtering for CIDR IP mask values /1 to /23, see the [Skip spam filtering for a CIDR IP outside of the available range](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) section later in this topic.</span></span>

     <span data-ttu-id="1bc06-148">IP アドレスまたはアドレス範囲を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="1bc06-148">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="1bc06-149">エントリを削除するには、[許可する IP アドレス] のエントリ **を選び** 、[削除] **をクリック** ![ します ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="1bc06-149">To remove an entry, select the entry in **Allowed IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="1bc06-150">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1bc06-150">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="1bc06-151">**IP 禁止一覧**: [編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1bc06-151">**IP Block List**: Click **Edit**.</span></span> <span data-ttu-id="1bc06-152">表示される**IP 禁止一**覧のポップアップで、IP 許可一覧の設定で説明したように、アドレス**Address or address range**またはアドレス範囲ボックスに単一の IP、IP アドレス範囲、または CIDR **IP を入力**します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-152">In the **IP Block List** flyout that appears, enter a single IP, IP range, or CIDR IP in the **Address or address range** box as previously described in the **IP Allow List** setting.</span></span>

     <span data-ttu-id="1bc06-153">IP アドレスまたはアドレス範囲を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="1bc06-153">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="1bc06-154">エントリを削除するには、[ブロックする IP アドレス] **内のエントリを選び** 、[削除] **をクリック** ![ します ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="1bc06-154">To remove an entry, select the entry in **Blocked IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="1bc06-155">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1bc06-155">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="1bc06-156">**セーフ リストを有効**にする: セーフ リストの使用を有効または無効にして、スパム フィルター処理をスキップする既知の適切な送信者を識別します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-156">**Turn on safe list**: Enable or disable the use of the safe list to identify known, good senders that will skip spam filtering.</span></span>

4. <span data-ttu-id="1bc06-157">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1bc06-157">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a><span data-ttu-id="1bc06-158">セキュリティ コンプライアンス センター&を使用して、既定の接続フィルター ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="1bc06-158">Use the Security & Compliance Center to view the default connection filter policy</span></span>

1. <span data-ttu-id="1bc06-159">セキュリティ コンプライアンス センター&、脅威管理**ポリシーの** \> **Policy** \> **スパム対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="1bc06-159">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="1bc06-160">[スパム **対策の設定] ページで** 、[接続フィルター ポリシー] という名前の既定のポリシーの横の **ドロップダウンをクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1bc06-160">On the **Anti-spam settings** page, click the drop down next to the default policy named **Connection filter policy**.</span></span>

3. <span data-ttu-id="1bc06-161">ポリシー設定がドロップダウンに表示され、そのテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bc06-161">The policy settings are displayed in the drop down that opens.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="1bc06-162">Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して既定の接続フィルター ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="1bc06-162">Use Exchange Online PowerShell or standalone EOP PowerShell to modify the default connection filter policy</span></span>

<span data-ttu-id="1bc06-163">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="1bc06-163">Use the following syntax:</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

<span data-ttu-id="1bc06-164">**注**:</span><span class="sxs-lookup"><span data-stu-id="1bc06-164">**Notes**:</span></span>

- <span data-ttu-id="1bc06-165">有効な IP アドレスまたはアドレスの範囲の値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1bc06-165">Valid IP address or address range values are:</span></span>

  - <span data-ttu-id="1bc06-166">単一の IP: 例: 192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="1bc06-166">Single IP: For example, 192.168.1.1.</span></span>

  - <span data-ttu-id="1bc06-167">IP 範囲: 例: 192.168.0.1 から 192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="1bc06-167">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

  - <span data-ttu-id="1bc06-168">CIDR IP:例: 192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="1bc06-168">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="1bc06-169">有効なネットワーク マスク値は /24 ~ /32 です。</span><span class="sxs-lookup"><span data-stu-id="1bc06-169">Valid network mask values are /24 through /32.</span></span>

- <span data-ttu-id="1bc06-170">指定 *した値で* 既存のエントリを上書きするには、次の構文を使用します `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 。</span><span class="sxs-lookup"><span data-stu-id="1bc06-170">To *overwrite* any existing entries with the values you specify, use the following syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`.</span></span>

- <span data-ttu-id="1bc06-171">他 *の既存のエントリに* 影響を及ぼせずに IP アドレスまたはアドレス範囲を追加または削除するには、次の構文を使用します `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 。</span><span class="sxs-lookup"><span data-stu-id="1bc06-171">To *add or remove* IP addresses or address ranges without affecting other existing entries, use the following syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`.</span></span>

- <span data-ttu-id="1bc06-172">IP 許可一覧または IP 禁止一覧を空にするには、値を使用します `$null` 。</span><span class="sxs-lookup"><span data-stu-id="1bc06-172">To empty the IP Allow List or IP Block List, use the value `$null`.</span></span>

<span data-ttu-id="1bc06-173">この例では、IP 許可一覧と IP 禁止一覧を指定された IP アドレスおよびアドレス範囲で構成します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-173">This example configures the IP Allow List and the IP Block List with the specified IP addresses and address ranges.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

<span data-ttu-id="1bc06-174">この例では、指定した IP アドレスおよびアドレス範囲を IP 許可一覧から追加および削除します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-174">This example adds and removes the specified IP addresses and address ranges from the IP Allow List.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

<span data-ttu-id="1bc06-175">構文およびパラメーターの詳細については [、「Set-HostedConnectionFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="1bc06-175">For detailed syntax and parameter information, see [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="1bc06-176">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="1bc06-176">How do you know this worked?</span></span>

<span data-ttu-id="1bc06-177">既定の接続フィルター ポリシーが正常に変更されたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-177">To verify that you've successfully modified the default connection filter policy, do any of the following steps:</span></span>

- <span data-ttu-id="1bc06-178">セキュリティ/コンプライアンス &で、[ **脅威**管理 \> **ポリシー** \> **のスパム対策]** に \> 移動し、接続フィルター **ポリシーの横にあるドロップ ダウンダウンをクリックし (常にオン)、** 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-178">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-Spam** \> click the drop down next to **Connection filter policy (always ON**), and verify the settings.</span></span>

- <span data-ttu-id="1bc06-179">Exchange Online PowerShell またはスタンドアロン EOP PowerShell で、次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-179">In Exchange Online PowerShell or standalone EOP PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- <span data-ttu-id="1bc06-180">IP 許可一覧のエントリからテスト メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-180">Send a test message from an entry on the IP Allow List.</span></span>

## <a name="additional-considerations-for-the-ip-allow-list"></a><span data-ttu-id="1bc06-181">IP 許可一覧の追加の考慮事項</span><span class="sxs-lookup"><span data-stu-id="1bc06-181">Additional considerations for the IP Allow List</span></span>

<span data-ttu-id="1bc06-182">次のセクションでは、IP 許可一覧を構成する際に知っておく必要があるその他の項目を示します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-182">The following sections identify additional items that you need to know about when you configure the IP Allow List.</span></span>

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a><span data-ttu-id="1bc06-183">使用可能な範囲外の CIDR IP アドレスに対するスパム フィルターをスキップする</span><span class="sxs-lookup"><span data-stu-id="1bc06-183">Skip spam filtering for a CIDR IP outside of the available range</span></span>

<span data-ttu-id="1bc06-184">前述したように、IP 許可一覧で使用できるのは、ネットワーク マスク /24 ~ /32 の CIDR IP のみです。</span><span class="sxs-lookup"><span data-stu-id="1bc06-184">As described earlier in this topic, you can only use a CIDR IP with the network mask /24 to /32 in the IP Allow List.</span></span> <span data-ttu-id="1bc06-185">送信元の電子メール サーバーから /23 範囲のソース 電子メール サーバーからのメッセージに対するスパム フィルターをスキップするには、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bc06-185">To skip spam filtering on messages from source email servers in the /1 to /23 range, you need to use Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="1bc06-186">ただし、可能な場合には、可能な場合には行わないことをお勧めします。なお、/1 ~ 23 CIDR の IP 範囲内の IP アドレスが Microsoft 独自の信頼できる禁止一覧またはサード パーティ製の任意のブロック リストに表示される場合にメッセージはブロックされるからです。</span><span class="sxs-lookup"><span data-stu-id="1bc06-186">But, we recommend that you don't do this if at all possible, because the messages will be blocked if an IP address in the /1 to /23 CIDR IP range appears on any of Microsoft's proprietary or third-party block lists.</span></span>

<span data-ttu-id="1bc06-187">潜在的な問題を完全に認識しているため、次の設定を使用してメール フロー ルールを作成し、これらの IP アドレスからのメッセージがスパム フィルター処理をスキップするようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1bc06-187">Now that you're fully aware of the potential issues, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from these IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="1bc06-188">ルールの条件:送信者 IP**アドレスがこれらの範囲**のいずれかまたは完全に一 \> **The sender** \> **致**する \> 場合に、このルールを適用します (/1 ~ /23 ネットワーク マスクで CIDR IP を入力します)。</span><span class="sxs-lookup"><span data-stu-id="1bc06-188">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (enter your CIDR IP with a /1 to /23 network mask).</span></span>

- <span data-ttu-id="1bc06-189">ルールの処理: **メッセージ プロパティを変更** \> **し、SCL (Spam Confidence Level)** でスパム \> **フィルターをバイパスします**。</span><span class="sxs-lookup"><span data-stu-id="1bc06-189">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

<span data-ttu-id="1bc06-190">ルールを監査したり、ルールをテストしたり、一定期間にルールをアクティブにしたり、その他の選択項目を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="1bc06-190">You can audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="1bc06-191">ルールを施行する前に一定期間ルールをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1bc06-191">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="1bc06-192">詳細については [、「Exchange Online のメール フロー ルールの管理」を参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="1bc06-192">For more information, see [Manage mail flow rules in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span>

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a><span data-ttu-id="1bc06-193">同じソースから選択的なメール ドメインに対するスパム フィルターをスキップする</span><span class="sxs-lookup"><span data-stu-id="1bc06-193">Skip spam filtering on selective email domains from the same source</span></span>

<span data-ttu-id="1bc06-194">通常、IP アドレスまたはアドレス範囲を IP 許可一覧に追加すると、そのメール ソースからのすべての受信メッセージを信頼できます。</span><span class="sxs-lookup"><span data-stu-id="1bc06-194">Typically, adding an IP address or address range to the IP Allow List means you trust all incoming messages from that email source.</span></span> <span data-ttu-id="1bc06-195">ただし、そのソースが複数のドメインから電子メールを送信し、その一部のドメインについてはスパム フィルターをスキップしたい場合があります。その他のドメインについてはスキップしたい場合はどうでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1bc06-195">But what if that source sends email from multiple domains, and you want to skip spam filtering for some of those domains, but not others?</span></span> <span data-ttu-id="1bc06-196">IP 許可一覧だけを使用してこの処理を行えることはできますが、IP 許可一覧をメール フロー ルールと組み合わせて使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1bc06-196">You can't use the IP Allow List alone to do this, but you can use the IP Allow List in combination with a mail flow rule.</span></span>

<span data-ttu-id="1bc06-197">たとえば、送信元電子メール サーバー 192.168.1.25 は contoso.com、fabrikam.com、および tailspintoys.com のドメインから電子メールを送信しますが、fabrikam.com の送信者からのメッセージに対するスパム フィルターをスキップする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1bc06-197">For example, the source email server 192.168.1.25 sends email from the domains contoso.com, fabrikam.com, and tailspintoys.com, but you only want to skip spam filtering for messages from senders in fabrikam.com.</span></span> <span data-ttu-id="1bc06-198">これを行うには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-198">To do this, use the following steps:</span></span>

1. <span data-ttu-id="1bc06-199">IP 許可一覧に 192.168.1.25 を追加します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-199">Add 192.168.1.25 to the IP Allow List.</span></span>

2. <span data-ttu-id="1bc06-200">次の設定 (最低でも) でメール フロー ルールを構成します:</span><span class="sxs-lookup"><span data-stu-id="1bc06-200">Configure a mail flow rule with the following settings (at a minimum):</span></span>

   - <span data-ttu-id="1bc06-201">ルールの条件:送信者 IP**アドレスがこのいずれかの**範囲に存在する場合、 \> **The sender** \> **IP address is in any of these ranges or exactly matches**または 192.168.1.25 (前の手順で IP 許可一覧に追加したのと同じ IP アドレスまたはアドレス範囲) に一致する \> 場合に、このルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-201">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (the same IP address or address range that you added to the IP Allow List in the previous step).</span></span>

   - <span data-ttu-id="1bc06-202">ルールの処理: **メッセージ プロパティを変更** \> **し、SCL (Spam Confidence Level) 0 を設定** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="1bc06-202">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **0**.</span></span>

   - <span data-ttu-id="1bc06-203">ルール例外: **送信者** \> **ドメインがドメインfabrikam.com** \> ドメインが無効である (スパム フィルタリングをスキップするドメインのみ)。</span><span class="sxs-lookup"><span data-stu-id="1bc06-203">Rule exception: **The sender** \> **domain is** \> fabrikam.com (only the domain or domains that you want to skip spam filtering).</span></span>

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a><span data-ttu-id="1bc06-204">IP 許可一覧のソースからのメッセージがフィルター処理を実行するシナリオ</span><span class="sxs-lookup"><span data-stu-id="1bc06-204">Scenarios where messages from sources in the IP Allow List are still filtered</span></span>

<span data-ttu-id="1bc06-205">IP 許可一覧内のメール サーバーからのメッセージは、引き続き次のシナリオでスパム フィルター処理の対象になります。</span><span class="sxs-lookup"><span data-stu-id="1bc06-205">Messages from an email server in your IP Allow List are still subject to spam filtering in the following scenarios:</span></span>

- <span data-ttu-id="1bc06-206">IP 許可一覧の IP アドレスは、オンプレミス、Microsoft 365 の任意のテナントの*any*IP ベースの受信コネクタ (このテナント A と呼**びます)、** およびメッセージを検出する前の EOP サーバーとも Microsoft データセンターの同じ*Active* Directory フォレスト内に存在するようになります。</span><span class="sxs-lookup"><span data-stu-id="1bc06-206">An IP address in your IP Allow List is also configured in an on-premises, IP-based inbound connector in *any* tenant in Microsoft 365 (let's call this Tenant A), **and** Tenant A and the EOP server that first encounters the message both happen to be in *the same* Active Directory forest in the Microsoft datacenters.</span></span> <span data-ttu-id="1bc06-207">このシナリオでは **、IPV:CAL** *が*[(メッセージ](anti-spam-message-headers.md)のスパム フィルター処理をバイパスしたことを示す) メッセージのスパム対策メッセージ ヘッダーに追加されますが、それでもメッセージはスパム フィルター処理の対象になります。</span><span class="sxs-lookup"><span data-stu-id="1bc06-207">In this scenario, **IPV:CAL** *is* added to the message's [anti-spam message headers](anti-spam-message-headers.md) (indicating the message bypassed spam filtering), but the message is still subject to spam filtering.</span></span>

- <span data-ttu-id="1bc06-208">IP 許可一覧を含むテナントと、最初にメッセージを検出した EOP サーバーは、両方とも Microsoft *データセンター* の異なる Active Directory フォレストに存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1bc06-208">Your tenant that contains the IP Allow List and the EOP server that first encounters the message both happen to be in *different* Active Directory forests in the Microsoft datacenters.</span></span> <span data-ttu-id="1bc06-209">このシナリオでは **、IPV:CAL** *がメッセージ* ヘッダーに追加されていないため、引き続きメッセージはスパム フィルター処理の対象になります。</span><span class="sxs-lookup"><span data-stu-id="1bc06-209">In this scenario, **IPV:CAL** *is not* added to the message headers, so the message is still subject to spam filtering.</span></span>

<span data-ttu-id="1bc06-210">これらのシナリオのいずれかに当てはなけた場合、以下の設定を満たすメール フロー ルールを作成して、問題がある IP アドレスからのメッセージがスパム フィルター処理をスキップするようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1bc06-210">If you encounter either of these scenarios, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from the problematic IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="1bc06-211">ルールの条件:送信者 IP**アドレスがこのいずれかの**範囲に存在する場合、または IP アドレスまたはアドレスと完全 \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> に一致する場合に、このルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="1bc06-211">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (your IP address or addresses).</span></span>

- <span data-ttu-id="1bc06-212">ルールの処理: **メッセージ プロパティを変更** \> **し、SCL (Spam Confidence Level)** でスパム \> **フィルターをバイパスします**。</span><span class="sxs-lookup"><span data-stu-id="1bc06-212">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

## <a name="new-to-microsoft-365"></a><span data-ttu-id="1bc06-213">Microsoft 365 を使用するのは?</span><span class="sxs-lookup"><span data-stu-id="1bc06-213">New to Microsoft 365?</span></span>

|<!-- a -->|
|---|
|<span data-ttu-id="1bc06-214">![LinkedIn Learning New ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **to Microsoft 365 の小さいアイコン**</span><span class="sxs-lookup"><span data-stu-id="1bc06-214">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="1bc06-215">LinkedIn Learning が提供する管理者および **IT**プロダッシー向けの無料のビデオ コースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1bc06-215">Discover free video courses for **Admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
|
