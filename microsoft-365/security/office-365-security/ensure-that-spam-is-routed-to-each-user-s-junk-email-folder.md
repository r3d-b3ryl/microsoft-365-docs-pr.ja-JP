---
title: スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection でスパムをユーザーの迷惑メールフォルダーにルーティングする方法について説明します。
ms.openlocfilehash: 6d1fd625669e8b638a408b2db1993f45fa653ffb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599364"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="03831-103">スパムが各ユーザーの 迷惑メール フォルダーに転送されるようにする</span><span class="sxs-lookup"><span data-stu-id="03831-103">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03831-p101">このトピックは、ハイブリッド展開でオンプレミスのメールボックスをホストしている Exchange Online Protection (EOP) のお客様にのみ当てはまります。Office 365 でメールボックスが完全にホストされている Exchange Online のお客様は、ここに示すコマンドを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="03831-p101">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment. Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span>

<span data-ttu-id="03831-106">EOP のお客様のための既定のスパム対策アクションでは、スパム メッセージは受信者の [迷惑メール] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="03831-106">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder.</span></span> <span data-ttu-id="03831-107">このアクションをオンプレミスのメールボックスで使用するには、オンプレミスのエッジサーバーまたはハブサーバーで Exchange メールフロールール (トランスポートルールとも呼ばれます) を構成して、EOP によって追加されたスパムヘッダーを検出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03831-107">In order for this action to work with on-premises mailboxes, you must configure Exchange mail flow rules (also known as transport rules) on your on-premises Edge or Hub servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="03831-108">これらのメールフロールールは、SclJunkThreshold コマンドレットのプロパティで使用されるスパム信頼レベル (SCL) を設定し、スパムを各メールボックスの迷惑メールフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="03831-108">These mail flow rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span>

### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="03831-109">Windows PowerShell を使用してスパムが迷惑メールフォルダーに移動されるようにメールフロールールを追加するには</span><span class="sxs-lookup"><span data-stu-id="03831-109">To add mail flow rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="03831-p103">オンプレミス Exchange サーバーの Exchange 管理シェル にアクセスします。オンプレミスの Exchange 組織で Exchange 管理シェル を開く方法については、「 **Open the Shell**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03831-p103">Access the Exchange Management Shell for your on-premises Exchange server. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>

2. <span data-ttu-id="03831-112">コンテンツでフィルターされたスパム メッセージを [迷惑メール] フォルダーにルーティングするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03831-112">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
   ```

   <span data-ttu-id="03831-113">ここで、 _Nameforrule_は新しいルールの名前です。たとえば、JunkContentFilteredMail。</span><span class="sxs-lookup"><span data-stu-id="03831-113">Where _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span>

3. <span data-ttu-id="03831-114">コンテンツ フィルターに到達する前にスパムとしてマークされたメッセージを [迷惑メール] フォルダーにルーティングするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03831-114">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
   ```

   <span data-ttu-id="03831-115">ここで、 _Nameforrule_は新しいルールの名前です。たとえば、JunkMailBeforeReachingContentFilter。</span><span class="sxs-lookup"><span data-stu-id="03831-115">Where _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span>

4. <span data-ttu-id="03831-116">次に示すコマンドを実行して、スパム フィルター ポリシーのブロック リスト ( **受信拒否送信者**一覧など) に登録されている送信者からのメッセージが [迷惑メール] フォルダーにルーティングされるようにします。</span><span class="sxs-lookup"><span data-stu-id="03831-116">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
   ```

   <span data-ttu-id="03831-117">ここで、 _Nameforrule_は新しいルールの名前です。たとえば、JunkMailInSenderBlockList。</span><span class="sxs-lookup"><span data-stu-id="03831-117">Where _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span>

<span data-ttu-id="03831-p104">**[迷惑メール フォルダーにメッセージを移動する]** アクションを使用しない場合は、Exchange 管理センター のコンテンツ フィルター ポリシーで別のアクションを選択してください。詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。メッセージ ヘッダー内で該当するフィールドの詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03831-p104">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

> [!TIP]
> <span data-ttu-id="03831-121">[**迷惑メールフォルダーにメッセージを移動**する] アクションを使用しない場合は、Exchange 管理センターのコンテンツフィルターポリシーで別のアクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="03831-121">If you don't want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="03831-122">詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03831-122">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="03831-123">メッセージ ヘッダー内で該当するフィールドの詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03831-123">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="03831-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="03831-124">See also</span></span>

[<span data-ttu-id="03831-125">New-transportrule</span><span class="sxs-lookup"><span data-stu-id="03831-125">New-TransportRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)
