---
title: Microsoft マネージド デスクトップ用に、印刷リソースを準備する
description: 印刷がスムーズに機能するための重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: b6e809505fed8b1f84eb502dc08751ad1f0b587c
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841401"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a><span data-ttu-id="a119e-104">Microsoft マネージド デスクトップ用に、印刷リソースを準備する</span><span class="sxs-lookup"><span data-stu-id="a119e-104">Prepare printing resources for Microsoft Managed Desktop</span></span>

<span data-ttu-id="a119e-105">Microsoft マネージド デスクトップに登録する準備ができたら、印刷要件を評価し、環境に適切なアプローチを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a119e-105">As you get ready to enroll in Microsoft Managed Desktop, you should evaluate your printing requirements and determine the right approach for your environment.</span></span> <span data-ttu-id="a119e-106">次の 3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a119e-106">You have three options:</span></span>
 
- <span data-ttu-id="a119e-107">Microsoft ユニバーサル印刷ソリューションを展開して、Microsoft マネージド デスクトップ デバイスでプリンターを簡単に検出できます。</span><span class="sxs-lookup"><span data-stu-id="a119e-107">Deploy the Microsoft Universal Print solution to make it easy for Microsoft Managed Desktop devices to discover printers.</span></span> <span data-ttu-id="a119e-108">詳細については、「ユニバーサル印刷 [とは」を参照してください](https://docs.microsoft.com/universal-print/fundamentals/universal-print-whatis)。</span><span class="sxs-lookup"><span data-stu-id="a119e-108">For more information, see [What is Universal Print](https://docs.microsoft.com/universal-print/fundamentals/universal-print-whatis).</span></span>
- <span data-ttu-id="a119e-109">カスタム PowerShell スクリプトを使用してプリンターを直接展開します。</span><span class="sxs-lookup"><span data-stu-id="a119e-109">Deploy printers directly by using a custom PowerShell script.</span></span> <span data-ttu-id="a119e-110">「ローカル プリンターのセットアップ [」セクションの手順に従](#set-up-local-printers) います。</span><span class="sxs-lookup"><span data-stu-id="a119e-110">Follow the steps in the [Set up local printers](#set-up-local-printers) section.</span></span>
- <span data-ttu-id="a119e-111">Azure Active Directory ドメインに参加している Windows 10 デバイスと互換性のある Microsoft 以外のクラウド印刷ソリューションを使用します。</span><span class="sxs-lookup"><span data-stu-id="a119e-111">Use a non-Microsoft cloud printing solution that is compatible with Windows 10 devices that are joined to an Azure Active Directory domain.</span></span> <span data-ttu-id="a119e-112">このソリューションは、Microsoft マネージド デスクトップのソフトウェア要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a119e-112">The solution must meet the software requirements for Microsoft Managed Desktop.</span></span> <span data-ttu-id="a119e-113">詳しくは [、Microsoft マネージド デスクトップ アプリの要件に関するページをご覧ください](../service-description/mmd-app-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a119e-113">For more information, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
 
<span data-ttu-id="a119e-114">すべての場合において、プリンター ドライバーが Microsoft Update または Microsoft Store から入手できない場合は、プリンター ドライバーを自分で入手し、Microsoft Intune を使用して Microsoft マネージド デスクトップ デバイスに展開するためにパッケージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a119e-114">In all cases, if the printer drivers are not available from Microsoft Update or the Microsoft Store, you'll have to obtain them yourself and have them packaged for deployment to your Microsoft Managed Desktop devices with Microsoft Intune.</span></span> <span data-ttu-id="a119e-115">詳しくは、「Intune スタンドアロン[- Win32 アプリ管理」をご覧ください](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)。</span><span class="sxs-lookup"><span data-stu-id="a119e-115">For more, see [Intune Standalone - Win32 app management](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)</span></span>

## <a name="set-up-local-printers"></a><span data-ttu-id="a119e-116">ローカル プリンターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="a119e-116">Set up local printers</span></span>

<span data-ttu-id="a119e-117">カスタム PowerShell スクリプトを使用してプリンターを展開し、印刷リソースを準備した場合は、次の手順に従って、共有プリンターを展開します。</span><span class="sxs-lookup"><span data-stu-id="a119e-117">If you've decided to deploy printers by using a custom PowerShell script and have prepared the printing resources, follow these steps to have shared printers deployed:</span></span>

1.  <span data-ttu-id="a119e-118">Microsoft マネージド デスクトップ ポータルに移動します。</span><span class="sxs-lookup"><span data-stu-id="a119e-118">Navigate to the Microsoft Managed Desktop portal.</span></span>
2.  <span data-ttu-id="a119e-119">管理ポータルのサポート> サポート要求セクションで、プリンターの展開というラベルの付いた要求を送信し、次の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="a119e-119">Submit a request labeled *Printer deployment* in the **Support > Support requests** section of the Admin Portal, providing these details:</span></span>
    - <span data-ttu-id="a119e-120">Microsoft マネージド デスクトップ デバイス用に展開する必要がある、プリンターの共有の場所への UNC パスすべて</span><span class="sxs-lookup"><span data-stu-id="a119e-120">All UNC paths to shared printer locations that will need to be deployed for Microsoft Managed Desktop devices</span></span>
    - <span data-ttu-id="a119e-121">これらの共有プリンターへのアクセスが必要なユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="a119e-121">User groups that require access to these shared printers</span></span>
3.  <span data-ttu-id="a119e-122">管理ポータルを使用して、要求が完了した時間をお知らせします。</span><span class="sxs-lookup"><span data-stu-id="a119e-122">Using the Admin Portal, we'll let you know when the request has been completed.</span></span> <span data-ttu-id="a119e-123">最初は、テスト展開グループのデバイスにのみ構成を展開します。</span><span class="sxs-lookup"><span data-stu-id="a119e-123">Initially we'll only deploy the configuration to devices in the Test deployment group.</span></span>
4.  <span data-ttu-id="a119e-124">構成が期待通り動作するかどうかをテストして確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a119e-124">You must test and confirm whether the configuration works as you expect.</span></span> <span data-ttu-id="a119e-125">テストが完了したら **、** サポート要求の [ディスカッション] タブを使用して返信します。</span><span class="sxs-lookup"><span data-stu-id="a119e-125">Reply by using the **Discussion** tab in the Support request to let us know when you've completed your testing.</span></span>
5.  <span data-ttu-id="a119e-126">その後、構成を他の展開グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="a119e-126">We'll then deploy the configuration to the other deployment groups.</span></span>
