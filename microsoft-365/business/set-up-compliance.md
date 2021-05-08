---
title: ユーザーの脅威保護を強化Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: コンプライアンス機能を設定して、データ損失を防止し、お客様と顧客の機密情報を安全に保ちます。
ms.openlocfilehash: 945f8a283b90b89da2fbe67a073e0807b80d198f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245086"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="d4056-103">コンプライアンス機能をセットアップする</span><span class="sxs-lookup"><span data-stu-id="d4056-103">Set up compliance features</span></span>

<span data-ttu-id="d4056-104">ユーザー Microsoft 365 Business Premiumデータとデバイスを保護し、ユーザーと顧客の機密情報を安全に保つ機能が付属しています。</span><span class="sxs-lookup"><span data-stu-id="d4056-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="d4056-105">DLP 機能のセットアップ</span><span class="sxs-lookup"><span data-stu-id="d4056-105">Set up DLP features</span></span>

<span data-ttu-id="d4056-106">個人 [データの損失から保護する](../compliance/create-a-dlp-policy-from-a-template.md) ポリシーを設定する方法の例については、「テンプレートから DLP ポリシーを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4056-106">See [Create a DLP policy from a template](../compliance/create-a-dlp-policy-from-a-template.md) for an example on how to set up a policy to protect against protect loss of personal data.</span></span> 
  
<span data-ttu-id="d4056-107">DLP には、多くの異なる地域ですぐに使用できるポリシー テンプレートが多数付属しています。</span><span class="sxs-lookup"><span data-stu-id="d4056-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="d4056-108">たとえば、オーストラリアの財務データ、カナダの個人情報法、米国の財務データなどです。</span><span class="sxs-lookup"><span data-stu-id="d4056-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="d4056-109">完全 [なリストについては、「DLP ポリシー テンプレートに含まれる](../compliance/what-the-dlp-policy-templates-include.md) もの」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4056-109">See [What the DLP policy templates include](../compliance/what-the-dlp-policy-templates-include.md) for a full list.</span></span> <span data-ttu-id="d4056-110">これらのテンプレートはすべて、PII テンプレートの例と同様に有効にできます。</span><span class="sxs-lookup"><span data-stu-id="d4056-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="d4056-111">メールの保持を設定するには、Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="d4056-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="d4056-112">**Exchange Online Archiving** 機能は、電子情報開示用の電子メール コンテンツを保持することで、コンプライアンスと規制の標準を維持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d4056-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="d4056-113">また、訴訟が発生した場合のリスクを軽減し、セキュリティ侵害後または削除済みアイテムを回復する必要がある場合にデータを回復する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4056-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="d4056-114">訴訟ホールドを使用して、すべてのユーザーのコンテンツを保持したり、保持ポリシーを使用して保持する内容をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="d4056-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="d4056-115">**訴訟ホールド:** ユーザーのメールボックス全体を訴訟ホールドに設定することで、削除済みアイテムを含むすべてのメールボックス コンテンツを保持できます。</span><span class="sxs-lookup"><span data-stu-id="d4056-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="d4056-116">メールボックスを訴訟ホールドに設定するには、管理センターで次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="d4056-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="d4056-117">左側のナビゲーションで、[ユーザーのアクティブな **ユーザー]** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="d4056-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="d4056-118">訴訟ホールドにメールボックスを配置するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4056-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="d4056-119">ユーザー ウィンドウで、[メールの設定]**を展開** し、[その他の設定] の横にある **[プロパティ** の編集] Exchange **します**。</span><span class="sxs-lookup"><span data-stu-id="d4056-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="d4056-120">ユーザーのメールボックス ページで、左側のナビゲーションで \*\* メールボックス機能 \*\* を選択し、[訴訟ホールド] の [有効にする] リンク **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d4056-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="d4056-121">[訴訟 **ホールド] ダイアログ** ボックスで、[訴訟ホールド期間] フィールドで訴訟ホールド **期間を指定** できます。</span><span class="sxs-lookup"><span data-stu-id="d4056-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="d4056-122">無限ホールドを設定する場合は、フィールドを空のままにします。</span><span class="sxs-lookup"><span data-stu-id="d4056-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="d4056-123">メモを追加して、訴訟ホールドの詳細を説明する必要がある Web サイトにメールボックスの所有者を指示できます。</span><span class="sxs-lookup"><span data-stu-id="d4056-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="d4056-124">\>**保存 .**</span><span class="sxs-lookup"><span data-stu-id="d4056-124">\> **Save**.</span></span>
    
<span data-ttu-id="d4056-125">**保持:** たとえば、カスタマイズした保持ポリシーを有効にして、特定の時間保持したり、保持期間の終わりにコンテンツを完全に削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="d4056-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="d4056-126">詳細については、「アイテム保持ポリシー [の概要」を参照してください](../compliance/retention.md)。</span><span class="sxs-lookup"><span data-stu-id="d4056-126">To learn more, see [Overview of retention policies](../compliance/retention.md).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="d4056-127">[感度ラベルの設定]</span><span class="sxs-lookup"><span data-stu-id="d4056-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="d4056-128">感度ラベルには、Azure Information Protection (AIP) プラン 1 が付き、ラベルを適用してドキュメントと電子メールを分類し、必要に応じて保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d4056-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="d4056-129">ラベルは、ルールと条件を定義する管理者、ユーザーが手動で、またはユーザーに推奨される組み合わせを使用して自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="d4056-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="d4056-130">[感度ラベル] を設定するには、[感度 [ラベルの作成と管理] ビデオを表示](../business-video/create-sensitivity-labels.md) します。</span><span class="sxs-lookup"><span data-stu-id="d4056-130">To set up Sensitivity labels, view [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="d4056-131">Azure Information Protection クライアントを手動でインストールする</span><span class="sxs-lookup"><span data-stu-id="d4056-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="d4056-132">AIP クライアントを手動でインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4056-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="d4056-133">Microsoft **ダウンロードAzinfoProtection_UL.exe** ダウンロード [センターからダウンロードします](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="d4056-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="d4056-134">Word ドキュメントを表示し、[ホーム] タブで [感度] オプションを使用して、インストールが機能したと **確認** できます。</span><span class="sxs-lookup"><span data-stu-id="d4056-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="d4056-135">![Word ドキュメントの [保護] タブ のドロップダウン。](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="d4056-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="d4056-136">詳細については、「クライアントのインストール [」を参照してください](/azure/information-protection/infoprotect-tutorial-step3)。</span><span class="sxs-lookup"><span data-stu-id="d4056-136">For more information, see [Install the client](/azure/information-protection/infoprotect-tutorial-step3).</span></span>