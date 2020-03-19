---
title: Microsoft マネージドデスクトップの印刷リソースの準備
description: 印刷がスムーズに機能するようにするための重要な手順
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a90d104915ecdd31d9ac35a6393fba74a3816ea8
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826439"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a><span data-ttu-id="356b6-104">Microsoft マネージドデスクトップの印刷リソースの準備</span><span class="sxs-lookup"><span data-stu-id="356b6-104">Prepare printing resources for Microsoft Managed Desktop</span></span>

<span data-ttu-id="356b6-105">Microsoft マネージドデスクトップに登録する準備ができたら、印刷要件を評価し、環境に適したアプローチを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="356b6-105">As you get ready to enroll in Microsoft Managed Desktop, you should evaluate your printing requirements and determine the right approach for your environment.</span></span> <span data-ttu-id="356b6-106">次の3つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="356b6-106">You have three options:</span></span>
 
- <span data-ttu-id="356b6-107">Microsoft ハイブリッドクラウド印刷ソリューションを展開して、Microsoft の管理されたデスクトップデバイスでプリンターを簡単に検出できるようにします。</span><span class="sxs-lookup"><span data-stu-id="356b6-107">Deploy the Microsoft hybrid cloud print solution to make it easy for Microsoft Managed Desktop devices to discover printers.</span></span> <span data-ttu-id="356b6-108">詳細については、「 [Deploy Windows Server ハイブリッド Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="356b6-108">For more information, see [Deploy Windows Server Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
- <span data-ttu-id="356b6-109">カスタム PowerShell スクリプトを使用して、プリンターを直接展開します。</span><span class="sxs-lookup"><span data-stu-id="356b6-109">Deploy printers directly by using a custom PowerShell script.</span></span> <span data-ttu-id="356b6-110">この操作を行うには、[[ローカルプリンターの設定](#set-up-local-printers)] セクションの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="356b6-110">Follow the steps in the [Set up local printers](#set-up-local-printers) section to do this.</span></span>
- <span data-ttu-id="356b6-111">Azure Active Directory ドメインに参加している Windows 10 デバイスと互換性のある Microsoft 以外のクラウド印刷ソリューションを使用します。</span><span class="sxs-lookup"><span data-stu-id="356b6-111">Use a non-Microsoft cloud printing solution that is compatible with Windows 10 devices that are joined to an Azure Active Directory domain.</span></span> <span data-ttu-id="356b6-112">ソリューションは、Microsoft マネージドデスクトップのソフトウェア要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="356b6-112">The solution must meet the software requirements for Microsoft Managed Desktop.</span></span> <span data-ttu-id="356b6-113">詳細については、「 [Microsoft Managed Desktop app の要件](../service-description/mmd-app-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="356b6-113">For more information, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
 
<span data-ttu-id="356b6-114">いずれの場合も、Microsoft Update または Microsoft ストアからプリンタードライバーを入手できない場合は、microsoft Intune を使用して Microsoft の管理されたデスクトップデバイスに展開するためにパッケージ化してパッケージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="356b6-114">In all cases, if the printer drivers are not available from Microsoft Update or the Microsoft Store, you'll have to obtain them yourself and have them packaged for deployment to your Microsoft Managed Desktop devices with Microsoft Intune.</span></span> <span data-ttu-id="356b6-115">詳細については、「 [Intune スタンドアロン-Win32 app management](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="356b6-115">For more, see [Intune Standalone - Win32 app management](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)</span></span>

## <a name="set-up-local-printers"></a><span data-ttu-id="356b6-116">ローカルプリンターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="356b6-116">Set up local printers</span></span>

<span data-ttu-id="356b6-117">カスタム PowerShell スクリプトを使用してプリンターを展開し、印刷リソースを準備している場合は、次の手順に従って共有プリンターを展開します。</span><span class="sxs-lookup"><span data-stu-id="356b6-117">If you've decided to deploy printers by using a custom PowerShell script and have prepared the printing resources, follow these steps to have shared printers deployed:</span></span>

1.  <span data-ttu-id="356b6-118">Microsoft マネージドデスクトップポータルに移動します。</span><span class="sxs-lookup"><span data-stu-id="356b6-118">Navigate to the Microsoft Managed Desktop portal.</span></span>
2.  <span data-ttu-id="356b6-119">管理ポータルの [ **support > support requests** ] セクションで、[*プリンター展開*] というラベルの付いた要求を送信し、次の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="356b6-119">Submit a request labeled *Printer deployment* in the **Support > Support requests** section of the Admin Portal, providing these details:</span></span>
    - <span data-ttu-id="356b6-120">Microsoft マネージドデスクトップデバイス用に展開する必要がある共有プリンターの場所へのすべての UNC パス</span><span class="sxs-lookup"><span data-stu-id="356b6-120">All UNC paths to shared printer locations that will need to be deployed for Microsoft Managed Desktop devices</span></span>
    - <span data-ttu-id="356b6-121">これらの共有プリンターにアクセスする必要があるユーザーグループ</span><span class="sxs-lookup"><span data-stu-id="356b6-121">User groups that require access to these shared printers</span></span>
3.  <span data-ttu-id="356b6-122">管理ポータルを使用すると、要求が完了したことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="356b6-122">Using the Admin Portal, we'll let you know when the request has been completed.</span></span> <span data-ttu-id="356b6-123">最初は、テスト展開グループのデバイスにのみ構成を展開します。</span><span class="sxs-lookup"><span data-stu-id="356b6-123">Initially we'll only deploy the configuration to devices in the Test deployment group.</span></span>
4.  <span data-ttu-id="356b6-124">構成が予想どおりに動作するかどうかをテストし、確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="356b6-124">You must test and confirm whether the configuration works as you expect.</span></span> <span data-ttu-id="356b6-125">[返信] サポート要求の [**ディスカッション**] タブを使用して、テストが完了したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="356b6-125">Reply by using the **Discussion** tab in the Support request to let us know when you've completed your testing.</span></span>
5.  <span data-ttu-id="356b6-126">その後、構成を他の展開グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="356b6-126">We'll then deploy the configuration to the other deployment groups.</span></span>
