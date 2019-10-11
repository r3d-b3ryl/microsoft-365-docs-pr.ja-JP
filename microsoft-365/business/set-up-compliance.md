---
title: Microsoft 365 Business の脅威保護を強化する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: コンプライアンス機能を設定して、データ損失を防ぎ、機密データにラベルを付けます。
ms.openlocfilehash: a0ba2fa6dbe7c786d577ad7098c1790f569f5acc
ms.sourcegitcommit: 255e8194bb5767a9983d54d16e79d628732a1d97
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2019
ms.locfileid: "37453920"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="b6b8d-103">コンプライアンス機能のセットアップ</span><span class="sxs-lookup"><span data-stu-id="b6b8d-103">Set up compliance features</span></span>

<span data-ttu-id="b6b8d-104">Microsoft 365 Business には、データとデバイスを保護するための機能が用意されており、お客様の機密情報を安全に保つために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="b6b8d-105">DLP 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="b6b8d-105">Set up DLP features</span></span>

<span data-ttu-id="b6b8d-106">個人を特定できる情報 (PII) を保護するポリシーを設定する方法の例については、「[テンプレートからの DLP ポリシーの作成](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="b6b8d-107">DLP には、さまざまなロケールに対して、多くの使用可能なポリシーテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="b6b8d-108">たとえば、オーストラリアの財務データ、カナダの個人情報法、米国金融データなど。完全なリストについては[、DLP ポリシーテンプレートに含まれるもの](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="b6b8d-109">これらのテンプレートはすべて、PII テンプレートの例と同様に有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="b6b8d-110">Exchange Online アーカイブを使用したメールの保存期間の設定</span><span class="sxs-lookup"><span data-stu-id="b6b8d-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="b6b8d-111">**Exchange Online のアーカイブ**ライセンス機能は、電子情報開示用の電子メールコンテンツを保持することで、コンプライアンスおよび規制基準を維持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="b6b8d-112">また、訴訟が発生した場合のリスクを軽減し、セキュリティ違反の後で、または削除済みアイテムを復元する必要がある場合にも、データを回復することができます。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="b6b8d-113">訴訟ホールドを使用して、ユーザーのすべてのコンテンツを保持するか、保持ポリシーを使用して、保持する内容をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="b6b8d-114">**訴訟ホールド:** ユーザーのメールボックスを訴訟ホールドの対象にすることで、削除されたアイテムを含むすべてのメールボックスのコンテンツを保持できます。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="b6b8d-115">メールボックスを訴訟ホールドの対象にするには、管理センターで次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="b6b8d-116">左側のナビゲーションで、[**ユーザー** \> ] [**アクティブなユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="b6b8d-117">訴訟ホールドの対象とするメールボックスを持つユーザーを選択し、ユーザーウィンドウで [**メールの設定**] を展開し、[**その他の設定**] の横にある [ **Exchange プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="b6b8d-118">ユーザーのメールボックスページで、左側のナビゲーションにある [\* \* メールボックスの機能] を選択し、[**訴訟ホールド**] の下の [**有効にする**] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="b6b8d-119">[**訴訟**ホールド] ダイアログボックスで、[**訴訟ホールド期間**] フィールドに訴訟ホールド期間を指定することができます。無限に保持する場合は、フィールドを空のままにします。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="b6b8d-120">また、メモを追加して、メールボックスの所有者を web サイトに誘導することもできます。 \>これにより、訴訟ホールドの**保存**について詳細に説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="b6b8d-121">**保持:** 保持期間の終了時に、特定の時間だけ保持したり、コンテンツを完全に削除したりするために、カスタマイズされた保持ポリシーを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="b6b8d-122">詳細については、「[アイテム保持ポリシーの概要](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="b6b8d-123">機密ラベルを設定する</span><span class="sxs-lookup"><span data-stu-id="b6b8d-123">Set up Sensitivity labels</span></span>

<span data-ttu-id="b6b8d-124">機密ラベルには、Azure Information Protection (AIP) プラン1が付属しており、ラベルを適用することにより、ドキュメントや電子メールを分類し、必要に応じて保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-124">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="b6b8d-125">ラベルは、ルールと条件を定義する管理者、またはユーザーによって手動で、またはユーザーに推奨事項を与える組み合わせを使用して、自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="b6b8d-126">機密ラベルを設定するには、「[感度ラベルを作成して管理](https://support.office.com/en-us/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)する」のビデオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-126">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.office.com/en-us/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="b6b8d-127">Azure Information Protection クライアントを手動でインストールする</span><span class="sxs-lookup"><span data-stu-id="b6b8d-127">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="b6b8d-128">AIP クライアントを手動でインストールするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-128">To manually install the AIP client:</span></span>

1. <span data-ttu-id="b6b8d-129">**AzinfoProtection_UL**を[Microsoft ダウンロードセンター](https://www.microsoft.com/download/details.aspx?id=53018)からダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-129">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="b6b8d-130">Word 文書を表示し、[**ホーム**] タブで [**秘密度**] オプションが有効になっていることを確認することで、インストールが正常に行われたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-130">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="b6b8d-131">![Word 文書内の [保護] タブのドロップダウン](media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="b6b8d-131">![Protection tab drop-down in a Word document.](media/word-sensitivity.png)</span></span>

<span data-ttu-id="b6b8d-132">詳細については、「[クライアントをインストールする](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b8d-132">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
