---
title: 通信エディターを使用する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: コンテンツの書式設定時にテキスト変数と結合フィールド変数を変更するには、コミュニケーション エディターを使用します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769162"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="c9b1d-103">通信エディターを使用する</span><span class="sxs-lookup"><span data-stu-id="c9b1d-103">Use the communications editor</span></span>

<span data-ttu-id="c9b1d-104">ポータル コンテンツ、法的ホールド通知、関連するアラーム/エスカレーションのコンテンツを定義する場合は、コミュニケーション エディターを使用してコンテンツの書式設定と動的なカスタマイズを行います。</span><span class="sxs-lookup"><span data-stu-id="c9b1d-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="c9b1d-105">リッチ テキスト エディター</span><span class="sxs-lookup"><span data-stu-id="c9b1d-105">Rich text editor</span></span>

<span data-ttu-id="c9b1d-106">コミュニケーション エディターを使用すると、エディター オプションを使用してテキストをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c9b1d-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="c9b1d-107">たとえば、ユーザーはフォントの種類を変更し、箇条書きリストを作成し、コンテンツを強調表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9b1d-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="c9b1d-108">フィールド変数の結合</span><span class="sxs-lookup"><span data-stu-id="c9b1d-108">Merge field variables</span></span>

<span data-ttu-id="c9b1d-109">コミュニケーション エディターの電子メール 差し込み変数を使用して、カスタマイズされた保管担当者の属性を通信の本文に埋め込みできます。</span><span class="sxs-lookup"><span data-stu-id="c9b1d-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="c9b1d-110">保管担当者に送信すると、マージ フィールドに対応するフィールドが設定されます。</span><span class="sxs-lookup"><span data-stu-id="c9b1d-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="c9b1d-111">たとえば、保管担当者 John Smith に送信すると、マージ フィールド [カストディアン名] が対応する名前で翻訳されます。</span><span class="sxs-lookup"><span data-stu-id="c9b1d-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="c9b1d-112">差し込み印刷フィールドを使用するには、リッチ テキスト エディター コントロールの上部にある [差し込み] フィールド アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9b1d-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="c9b1d-113">プレースホルダーは、ユーザーのカーソルの位置に基づいて追加されます。</span><span class="sxs-lookup"><span data-stu-id="c9b1d-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="c9b1d-114">差し込みフィールド変数の一覧</span><span class="sxs-lookup"><span data-stu-id="c9b1d-114">List of merge field variables</span></span>

| <span data-ttu-id="c9b1d-115">フィールド名</span><span class="sxs-lookup"><span data-stu-id="c9b1d-115">Field name</span></span>                  | <span data-ttu-id="c9b1d-116">フィールドの詳細</span><span class="sxs-lookup"><span data-stu-id="c9b1d-116">Field details</span></span> |
| :------------------- | :------------------- |
| <span data-ttu-id="c9b1d-117">表示名</span><span class="sxs-lookup"><span data-stu-id="c9b1d-117">Display Name</span></span>  | <span data-ttu-id="c9b1d-118">カストディアンの名と名。</span><span class="sxs-lookup"><span data-stu-id="c9b1d-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="c9b1d-119">受信確認リンク</span><span class="sxs-lookup"><span data-stu-id="c9b1d-119">Acknowledgment Link</span></span> | <span data-ttu-id="c9b1d-120">各保管担当者の確認を記録するカスタマイズされたリンク。</span><span class="sxs-lookup"><span data-stu-id="c9b1d-120">A customized link to record each custodian's acknowledgment.</span></span>|                 |
| <span data-ttu-id="c9b1d-121">ポータル リンク</span><span class="sxs-lookup"><span data-stu-id="c9b1d-121">Portal Link</span></span>     | <span data-ttu-id="c9b1d-122">保管担当者のコンプライアンス ポータルのカスタマイズされたリンク。</span><span class="sxs-lookup"><span data-stu-id="c9b1d-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="c9b1d-123">発行責任者</span><span class="sxs-lookup"><span data-stu-id="c9b1d-123">Issuing Officer</span></span>                   | <span data-ttu-id="c9b1d-124">指定された発行担当者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="c9b1d-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="c9b1d-125">発行日</span><span class="sxs-lookup"><span data-stu-id="c9b1d-125">Issuing Date</span></span>                   | <span data-ttu-id="c9b1d-126">通知が発行された日付 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="c9b1d-126">The date that the notice was issued (UTC).</span></span>              |
|||
