---
title: Cortana と Office 365 の統合
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7257cb50-0d5c-4f7a-ac2e-9fe5d13bb5cb
description: 'Cortana を使用する方法については、「Office 365 と統合されている場合」を参照してください。 管理センターで Cortana をオフにして、組織のデータへのアクセスを制限することができます。 '
ms.openlocfilehash: 8f20c9b96ee57dcdf5da99dc08ffeb72465bc515
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361438"
---
# <a name="cortana-in-office-365"></a><span data-ttu-id="4f02b-104">Office 365 の Cortana</span><span class="sxs-lookup"><span data-stu-id="4f02b-104">Cortana in Office 365</span></span>

<span data-ttu-id="4f02b-105">Cortana は、デバイスと Microsoft サービスを経由して動作する、クラウドベースのデジタルアシスタントと Microsoft 365 および Office 365 サービスです。</span><span class="sxs-lookup"><span data-stu-id="4f02b-105">Cortana is a cloud-based digital assistant and Microsoft 365 and Office 365 service that works across your devices and Microsoft services.</span></span> <span data-ttu-id="4f02b-106">Cortana は、Microsoft 365 および Office 365 に格納されている情報を使用して、組織内のユーザーが最新の状態を維持したり、洞察、提案されたタスク、および会議、ドキュメント、連絡先に関するヘルプを取得したりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4f02b-106">Cortana can use information stored in Microsoft 365 and Office 365 to help people in your organization stay up to date and get insights, suggested tasks, and help with their meetings, documents, and contacts.</span></span>
  
## <a name="info-for-admins"></a><span data-ttu-id="4f02b-107">管理者向け情報</span><span class="sxs-lookup"><span data-stu-id="4f02b-107">Info for admins</span></span>

<span data-ttu-id="4f02b-108">コンプライアンスは、Microsoft が企業のお客様に提供するコミットメントです。</span><span class="sxs-lookup"><span data-stu-id="4f02b-108">Compliance is a commitment that Microsoft makes to enterprise customers.</span></span> [<span data-ttu-id="4f02b-109">詳細については、「Microsoft コンプライアンスフレームワーク」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f02b-109">Learn more about the Microsoft compliance framework.</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=2109173)

<span data-ttu-id="4f02b-110">他の Microsoft 365 および Office 365 サービスとの間では、準拠している Cortana 機能は保護され、偶発的な損失からのユーザーデータの保護を含む一連の約束、変更、許可されていない開示またはアクセス、または違法な破壊。</span><span class="sxs-lookup"><span data-stu-id="4f02b-110">Consistent with other Microsoft 365 and Office 365 services, compliant Cortana features are protected and secured subject to the Online Service Terms that includes a set of promises involving protection of user data against accidental loss, alteration, unauthorized disclosure or access, or unlawful destruction.</span></span> <span data-ttu-id="4f02b-111">他のすべての Cortana 機能 (Cortana オプション接続サービスなど) は、 [Microsoft サービス規約](https://go.microsoft.com/fwlink/p/?LinkId=2109174)および Microsoft の[プライバシー](https://go.microsoft.com/fwlink/p/?LinkId=2109175)に関する声明の対象となります。</span><span class="sxs-lookup"><span data-stu-id="4f02b-111">All other Cortana features (i.e., Cortana optional connected services) are subject to the [Microsoft Services Agreement](https://go.microsoft.com/fwlink/p/?LinkId=2109174) and  [Microsoft Privacy Statement.](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span></span>

<span data-ttu-id="4f02b-112">Cortana サービスは、**準拠**し、**オプションで接続さ**れたサービスという2つのデータカテゴリに分かれています。これらを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="4f02b-112">Cortana services are broken into two data categories, **compliant** and **optional connected services**, which you can control.</span></span>

## <a name="turn-off-cortana-optional-connected-services"></a><span data-ttu-id="4f02b-113">Cortana オプションの接続されたサービスをオフにする</span><span class="sxs-lookup"><span data-stu-id="4f02b-113">Turn off Cortana optional connected services</span></span>

<span data-ttu-id="4f02b-114">組織の従業員に対して、Cortana オプションの接続されたサービスをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f02b-114">Cortana optional connected services can be turned off for employees at your organization.</span></span> <span data-ttu-id="4f02b-115">これにより、Windows と Cortana モバイルアプリの cortana でのオプションの接続サービス (Cortana) を無効にします。</span><span class="sxs-lookup"><span data-stu-id="4f02b-115">This will disable Cortana optional connected services in Cortana on Windows and the Cortana mobile app.</span></span> <span data-ttu-id="4f02b-116">これには、Cortana のアラーム、リスト、タスク、およびその他の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f02b-116">This includes Cortana reminders, lists, tasks, and other features.</span></span> <span data-ttu-id="4f02b-117">Cortana のブリーフィングメールや Outlook mobile での電子メールの再生など、準拠しているカテゴリ (Cortana OST エクスペリエンス) のサービスは、アクティブのままになります。</span><span class="sxs-lookup"><span data-stu-id="4f02b-117">Services in the compliant category (i.e., Cortana OST experiences), such as Cortana’s Briefing email, and Play My Emails in Outlook mobile, will remain active.</span></span>

1. <span data-ttu-id="4f02b-118">Microsoft 365 管理センターで、[**設定** > の**設定**] を選択し、[ **Cortana**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f02b-118">In the Microsoft 365 admin center, select **Settings** > **Settings** and select **Cortana**.</span></span>

4. <span data-ttu-id="4f02b-119">[ **Cortana による接続のエクスペリエンスを許可**する] チェックボックスをオンにして、cortana との接続エクスペリエンスを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="4f02b-119">Select the checkbox for **Allow Cortana optional connected experiences to use your organizations's Microsoft hosted data** to enable or disable Cortana connected experiences.</span></span>

5. <span data-ttu-id="4f02b-120">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f02b-120">Select **Save changes**.</span></span>

## <a name="turn-off-cortana-ost-experiences"></a><span data-ttu-id="4f02b-121">Cortana OST エクスペリエンスをオフにする</span><span class="sxs-lookup"><span data-stu-id="4f02b-121">Turn off Cortana OST experiences</span></span>

<span data-ttu-id="4f02b-122">組織の従業員は、以下の手順に従って、Cortana OST エクスペリエンスを個別に選択することができます。</span><span class="sxs-lookup"><span data-stu-id="4f02b-122">Your organization's employees can opt out of Cortana OST experiences individually by following the steps below.</span></span>

1. <span data-ttu-id="4f02b-123">Outlook mobile を開きます。</span><span class="sxs-lookup"><span data-stu-id="4f02b-123">Open Outlook mobile.</span></span>

2. <span data-ttu-id="4f02b-124">[**設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4f02b-124">Go to **Settings**.</span></span>
  
3. <span data-ttu-id="4f02b-125">[**メールを再生**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f02b-125">Select **Play My Emails**.</span></span>

4. <span data-ttu-id="4f02b-126">無効にするアカウントの切り替えを [オフ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4f02b-126">Move the toggle to off on the accounts you want to disable.</span></span>

### <a name="briefing-email"></a><span data-ttu-id="4f02b-127">ブリーフィング電子メール</span><span class="sxs-lookup"><span data-stu-id="4f02b-127">Briefing email</span></span>

<span data-ttu-id="4f02b-128">タスクバーで Cortana を無効にしても、Cortana のブリーフィングメールは無効になりません。</span><span class="sxs-lookup"><span data-stu-id="4f02b-128">Disabling Cortana on the taskbar won't disable Cortana’s Briefing email.</span></span> <span data-ttu-id="4f02b-129">従業員は個別に登録を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f02b-129">Employees must unsubscribe individually.</span></span> <span data-ttu-id="4f02b-130">組織の個人は、メッセージのフッターで [**購読取り消し**] を選択することによって、Cortana のブリーフィングメールをオプトアウトできます。</span><span class="sxs-lookup"><span data-stu-id="4f02b-130">Individuals from your organization can opt out of Cortana’s Briefing email by selecting **Unsubscribe** in the footer of the message.</span></span>
