---
title: Microsoft マネージドデスクトップの構成可能な設定
description: Microsoft マネージドデスクトップの構成可能な設定に関する情報
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント、設定、構成可能な設定
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.openlocfilehash: 64560a1eb597072dd99c1538b0131e3cd807899c
ms.sourcegitcommit: 1942a860d1b65e1f8062564ec4703b953e0c2fd7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30122247"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="7db22-104">構成可能な設定-Microsoft マネージドデスクトップ</span><span class="sxs-lookup"><span data-stu-id="7db22-104">Configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="7db22-p101">microsoft マネージドデスクトップは、microsoft マネージドデスクトップによって管理されるすべてのデバイスに適用される設定とポリシーを展開します。詳細については、「[デバイスの構成](../service-description/device-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7db22-p101">Microsoft Managed Desktop deploys settings and policies that are applied to all devices managed by Microsoft Managed Desktop. For more information, see [Device configuration](../service-description/device-policies.md).</span></span>

<span data-ttu-id="7db22-p102">Microsoft マネージドデスクトップの構成可能な設定を使用すると、組織およびビジネスのニーズに固有の設定をカスタマイズおよび展開することができるようになります。これらの設定は、Microsoft マネージドデスクトップで管理されるデバイスの構成設定とポリシーに加えています。</span><span class="sxs-lookup"><span data-stu-id="7db22-p102">Configurable settings in Microsoft Managed Desktop give IT admins a way to customize and deploy settings that are unique to their organization and business needs. These settings are in addition to device configuration settings and policies that are managed by Microsoft Managed Desktop.</span></span>  

<span data-ttu-id="7db22-p103">構成可能な設定変更がクラウドで行われ、定義された展開リングで Microsoft マネージドデスクトップデバイスに適用されます。このプロセスは、Microsoft Managed Desktop が、サービスによって定義および管理されているデバイス構成の設定とポリシーに対する変更を管理する方法に似ています。Microsoft Managed Desktop が変更を展開するために使用するのと同じプロセスを使用することにより、モダンな IT 管理方法を使用して引き続き組織を移行します。</span><span class="sxs-lookup"><span data-stu-id="7db22-p103">Configurable setting changes are made in the cloud and applied to your Microsoft Managed Desktop devices in defined deployment rings. This process is similar to how Microsoft Managed Desktop manages changes to device configuruation settings and policies that are defined and managed by the service. By using the same process that Microsoft Managed Desktop uses for deploying changes,you continue to move your organization forward, using modern IT management practices.</span></span>

## <a name="when-to-use-configurable-settings"></a><span data-ttu-id="7db22-112">構成可能な設定を使用する場合</span><span class="sxs-lookup"><span data-stu-id="7db22-112">When to use configurable settings?</span></span>

<span data-ttu-id="7db22-113">構成可能な設定を使用するには、いくつかの回数があります。</span><span class="sxs-lookup"><span data-stu-id="7db22-113">There are a few times to use configurable settings.</span></span> 

<span data-ttu-id="7db22-p104">**オンボードプロセス**– microsoft managed desktop service に展開する場合、または多数のデバイス (20 以上) をオンにした場合に、構成可能な設定をカスタマイズすることをお勧めします。カテゴリの設定は、Microsoft Managed Desktop admin portal で構成されます。利用を作成し、管理ポータルにアクセスすると、組織に合わせてカスタマイズする設定カテゴリを決定し、変更を行って、展開をステージした後、変更を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="7db22-p104">**Onboarding process** – Microsoft Managed Desktop recommends that you customize configurable settings when you onboard to Microsoft Managed Desktop service, or when you onboard a large number of devices (20 or more). Setting categories are configured in Microsoft Managed Desktop admin portal. After you’ve onboarded and have access to the admin portal, you can decide which setting categories you want to customize for your organization, make the changes, stage a deployment, and then deploy your changes.</span></span>

<span data-ttu-id="7db22-p105">**設定を管理**する-設定を定期的に確認し、必要な更新を行います。業務上の変更をサポートするために変更を加える必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7db22-p105">**Maintain settings** - Review your settings regularly and make needed updates. You might need to make changes to support a change in your business.</span></span>   

## <a name="setting-categories"></a><span data-ttu-id="7db22-119">カテゴリの設定</span><span class="sxs-lookup"><span data-stu-id="7db22-119">Setting categories</span></span>

<span data-ttu-id="7db22-120">カスタマイズ可能な設定カテゴリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7db22-120">These are the configurable settings categories that you can customize:</span></span>
- <span data-ttu-id="7db22-121">[デスクトップの背景画像](config-setting-ref.md#desktop-background-picture)– Microsoft マネージドデスクトップデバイスのデスクトップの背景画像をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="7db22-121">[Desktop background picture](config-setting-ref.md#desktop-background-picture) – Customize the desktop background picture for Microsoft Managed Desktop devices.</span></span> 
- <span data-ttu-id="7db22-p106">[ブラウザーの開始ページ](config-setting-ref.md#browser-start-pages)– Microsoft Edge で使用する開始ページを追加します。ブラウザーのスタートページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7db22-p106">[Browser start pages](config-setting-ref.md#browser-start-pages) – Add start pages to use with Microsoft Edge. See Browser start page</span></span>
- <span data-ttu-id="7db22-p107">[エンタープライズモードのサイトリスト](config-setting-ref.md#enterprise-mode-site-list-location)-サイトを追加し、その互換性モードを追加します。リスト上のサイトは、Internet Explorer で開始されます。</span><span class="sxs-lookup"><span data-stu-id="7db22-p107">[Enterprise mode site list](config-setting-ref.md#enterprise-mode-site-list-location) – Add sites, and their compatibility mode. Sites on the list will start in Internet Explorer.</span></span> 
- <span data-ttu-id="7db22-126">[[信頼済みサイト](config-setting-ref.md#trusted-sites)] –信頼済みサイトを追加し、各サイトのセキュリティゾーンを設定します。</span><span class="sxs-lookup"><span data-stu-id="7db22-126">[Trusted sites](config-setting-ref.md#trusted-sites) – Add trusted sites and set security zones for each site.</span></span> 
- <span data-ttu-id="7db22-127">[プロキシサイトの例外](config-setting-ref.md#proxy)–プロキシサーバーのアドレス番号とポート番号を設定し、プロキシサイトの例外を追加します。</span><span class="sxs-lookup"><span data-stu-id="7db22-127">[Proxy site exceptions](config-setting-ref.md#proxy) – Set up your proxy server address number and port number, and add proxy site exceptions.</span></span>

<span data-ttu-id="7db22-p108">各設定カテゴリは、独自にカスタマイズして展開することができます。複数の設定カテゴリに変更を同時に展開することはできますが、設定カテゴリに一度に展開できるのは一度に1つだけです。</span><span class="sxs-lookup"><span data-stu-id="7db22-p108">Each setting category can be customized and deployed on its own. You can deploy changes to multiple setting categories at the same time, however, you can only deploy one change at a time to a setting category.</span></span>

<span data-ttu-id="7db22-130">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7db22-130">For example:</span></span>
- <span data-ttu-id="7db22-131">デスクトップの背景画像と信頼済みサイトへの変更は、それぞれ独自の展開として同時に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="7db22-131">You can deploy changes to desktop background picture and trusted sites, each as their own deployment, at the same time.</span></span> 
- <span data-ttu-id="7db22-p109">2つの展開を同時にブラウザー開始ページに展開することはできません。最新の展開では、進行中の以前の展開が停止されます。</span><span class="sxs-lookup"><span data-stu-id="7db22-p109">You can’t deploy two deployments to browser start pages at the same time. The most recent deployment will stop earlier deployments that are still in progress.</span></span>

## <a name="configurable-setting-process"></a><span data-ttu-id="7db22-134">構成可能な設定プロセス</span><span class="sxs-lookup"><span data-stu-id="7db22-134">Configurable setting process</span></span>

<span data-ttu-id="7db22-135">全体的なプロセスは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7db22-135">The overall process looks like this.</span></span> 

<span data-ttu-id="7db22-p110">**ステップ 1-計画**-構成可能な設定について説明し、組織に対して構成する設定カテゴリを決定します。内部の変更管理プロセスに適合するユーザーへの通信を計画します。たとえば、ブラウザーのスタートページを追加する場合は、展開後にブラウザーにスタートページの新しいセットがあることをユーザーに知らせてください。</span><span class="sxs-lookup"><span data-stu-id="7db22-p110">**Step 1 - Plan** - Learn about configurable settings and decide which setting categories you want to configure for your organization. Plan communication to your users that meets your internal change management processes. For example, if you're adding browser start pages, let your users know that they'll have a new set of start pages in their browser after the deployment.</span></span>  

<span data-ttu-id="7db22-p111">**手順 2-展開の構成とステージング**-Microsoft Managed Desktop 管理ポータルの構成可能な設定に変更を加えます。変更をステージして、展開の準備をします。変更についてユーザーに知らせ、変更によってデバイスの操作がどのように変化するかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7db22-p111">**Step 2 - Configure and stage deployment** - Make changes to configurable settings in Microsoft Managed Desktop admin portal. Stage the changes so they’re ready to deploy. Remember to let your users know about the changes, and how the changes will change their device experience.</span></span>   

<span data-ttu-id="7db22-p112">Microsoft Managed Desktop 管理ポータルで変更を構成し、ステージングします。詳細については、「[構成可能な設定をカスタマイズ](config-setting-ref.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7db22-p112">You configure and stage changes in the Microsoft Managed Desktop admin portal. For more information, see [Customize configurable settings](config-setting-ref.md).</span></span> 

<span data-ttu-id="7db22-p113">**手順 3-変更内容を伝達**するユーザーに関する今後の変更についての情報を伝達します。展開ごとに、変更管理プロセスの一部である通信を完了します。ユーザーがどのように機能するか、またはデバイスに表示される内容に影響を与える変更を明確に伝える必要があります。</span><span class="sxs-lookup"><span data-stu-id="7db22-p113">**Step 3 - Communicate changes** Communicate information about upcoming changes to your users. For each deployment, complete the communication that is part of your change management processes. You should clearly communicate any change that impacts how a user works, or what they will see on their devices.</span></span>

<span data-ttu-id="7db22-p114">**手順 4-変更の展開**-テストリングから始めて変更を展開します。このテストリングを使用すると、より多くのデバイスのグループへの変更を展開する前に、より少ないデバイスで、リングの問題を検証し、トラブルシューティングを行うことができます。問題が発生した場合は、変更を元に戻し、設定を更新して、新しい展開をステージングすることができます。Microsoft マネージドデスクトップでは、構造化された手法を使用して、次の順序で呼び出しを展開することをお勧めします。テスト、ファースト、Fast、および広範。</span><span class="sxs-lookup"><span data-stu-id="7db22-p114">**Step 4 - Deploy changes** – Deploy your changes, starting with the Test ring. The Test ring allows you to validate and troubleshoot any issues in a ring with fewer devices, before deploying changes to larger groups of devices. If you run into any issues, you can revert the change, update the setting, and stage a new deployment. Microsoft Managed Desktop recommends that you follow the structured approach and deploy to rings in this order: Test, First, Fast, and then Broad.</span></span>   

<span data-ttu-id="7db22-p115">構成可能なすべての設定は、Microsoft managed Desktop 管理ポータルを使用して管理されます。詳細については、「[変更を展開](config-setting-deploy.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7db22-p115">All configurable settings are managed using the Microsoft Managed Desktop admin portal. For more information, see [Deploy changes](config-setting-deploy.md).</span></span> 

<span data-ttu-id="7db22-p116">**ステップ 5-変更の追跡**-展開状態に対する変更の進行状況を追跡します。各設定に対して、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7db22-p116">**Step 5 - Track changes** – Track the progress for your changes on Deployment status. For each setting, you can:</span></span>
- <span data-ttu-id="7db22-p117">**進捗状況を追跡**する-変更を展開した後に状態を追跡します。状態は [**進行**中] に変わり、**完了**するか、**失敗**します。展開に失敗した場合は、Microsoft マネージドデスクトップ操作のサポート要求が自動的に開かれ、問題を調査します。</span><span class="sxs-lookup"><span data-stu-id="7db22-p117">**Track progress** – Track status after you deploy the change. The status will change to **In progress**, and then either **Complete**, or **Failed**. If a deployment fails, a support request is automatically opened for Microsoft Managed Desktop Operations to investigate the issue.</span></span>  
- <span data-ttu-id="7db22-158">展開された**バージョンを参照**: 展開された変更ごとにバージョン番号があります。</span><span class="sxs-lookup"><span data-stu-id="7db22-158">**See version deployed** – Each deployed change has a version number.</span></span>
- <span data-ttu-id="7db22-p118">**変更を元に戻す**-変更を元に戻す現在の展開を停止し、すべての呼び出しに展開された最後の変更にすべての呼び出しを戻します。前回正常起動時の設定値にロールバックしています。</span><span class="sxs-lookup"><span data-stu-id="7db22-p118">**Revert changes** – Reverting a change stops the current deployment, and reverts all rings to the last changes that was deployed to all rings. You are rolling back to the last-known-good setting value.</span></span>
- <span data-ttu-id="7db22-161">**変更を検証**する-展開が完了したら、変更が予想どおりに適用されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7db22-161">**Validate changes** - After the deployment is complete, validate the changes were applied as you expected.</span></span>  

<span data-ttu-id="7db22-162">展開が失敗した場合、または変更を元に戻すことができない場合は、Microsoft マネージドデスクトップ操作を使用して[サポート要求を開き](admin-support.md)ます。</span><span class="sxs-lookup"><span data-stu-id="7db22-162">If a deployment has failed, or you can't revert a change, [open a support request](admin-support.md) with Microsoft Managed Desktop Operations.</span></span> 

<span data-ttu-id="7db22-163">詳細については、「[構成可能な設定を展開および追跡](config-setting-deploy.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7db22-163">For more information, see [Deploy and track configurable settings](config-setting-deploy.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7db22-164">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="7db22-164">Additional resources</span></span>
- [<span data-ttu-id="7db22-165">構成可能な設定のリファレンス</span><span class="sxs-lookup"><span data-stu-id="7db22-165">Configurable settings reference</span></span>](config-setting-ref.md) 
- [<span data-ttu-id="7db22-166">構成可能な設定を展開する</span><span class="sxs-lookup"><span data-stu-id="7db22-166">Deploy configurable settings</span></span>](config-setting-deploy.md) 
