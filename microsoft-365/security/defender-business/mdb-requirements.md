---
title: Microsoft Defender for Businessの要件
description: Microsoft Defender for Businessライセンス、ハードウェア、ソフトウェアの要件
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/09/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365solution-mdb-setup
ms.openlocfilehash: 20de14ce0357ecb28a205d1699a8756b78e542aa
ms.sourcegitcommit: 6bff75867764335685f972943170c7db46e33a6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "67301274"
---
# <a name="microsoft-defender-for-business-requirements"></a>Microsoft Defender for Business要件

この記事では、Defender for Business の要件について説明します。

## <a name="what-to-do"></a>操作

1. [要件を確認し、要件を満たしていることを確認します](#review-the-requirements)。
2. [次の手順に進みます](#next-steps)。


## <a name="review-the-requirements"></a>システム要件を確認する

次の表に、Defender for Business を構成して使用するために必要な基本的な要件を示します。

| 要件 | 説明 |
|:---|:---|
| サブスクリプション | Microsoft 365 Business Premiumまたは Defender for Business (スタンドアロン)。 [Defender for Business を取得する方法に関する説明を](get-defender-business.md)参照してください。  |
| Datacenter | 次のいずれかのデータセンターの場所。 <ul><li>欧州連合</li><li>英国</li><li>米国</li></ul> |
| ユーザー アカウント |<ul><li>ユーザー アカウントは、Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) に作成されます。</li><li>Defender for Business (またはMicrosoft 365 Business Premium) のライセンスは、Microsoft 365 管理センターに割り当てられます。</li></ul>このタスクのヘルプについては、「ユーザーの [追加とライセンスの割り当て](mdb-add-users.md)」を参照してください。 |
| アクセス許可  | Defender for Business にサインアップするには、グローバル 管理である必要があります。<br/><br/>Microsoft 365 Defender ポータルにアクセスするには、[Azure AD で](mdb-roles-permissions.md)次のいずれかのロールが割り当てられている必要があります。<ul><li>セキュリティ閲覧者</li><li>セキュリティ管理者</li><li>グローバル管理者</li></ul>詳細については、「 [Defender for Business のロールとアクセス許可」を](mdb-roles-permissions.md)参照してください。 |
| ブラウザー要件 | Microsoft Edge または Google Chrome |
| クライアント デバイス オペレーティング システム | Microsoft 365 Defender ポータルでデバイスを管理するには、デバイスが次のいずれかのオペレーティング システムを実行している必要があります。 <ul><li>Windows 10または 11 Business</li><li>Windows 10または 11 Professional</li><li>Windows 10または 11 Enterprise</li><li>Mac (最新の 3 つのリリースがサポートされています)</li></ul><br/><br/>WINDOWS デバイスに [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) がインストールされていることを確認します。 <br/><br/>Microsoft Intuneでデバイスを既に管理している場合は、Microsoft エンドポイント マネージャー管理センターを引き続き使用できます。 その場合、次の他のオペレーティング システムがサポートされます。 <ul><li>iOS と iPadOS</li><li>Android OS</li></ul> |
| サーバーの要件 | Windows Server または Linux Server のインスタンスのオンボードを計画している場合は、次の要件を満たしている必要があります。 <ul><li>**[プレビュー機能]** 設定がオンになっています。 Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で、**[設定]** > **[エンドポイント]** > **[全般]** > **[高度な機能]****[プレビュー機能]** >  の順に移動します。</li><li>Windows Server の適用スコープが有効になっています。 Microsoft 365 Defender ポータルで、[**設定** > **エンドポイント** > **の構成管理** > **の適用] スコープ** に移動します。 **[MDE を使用して MEM からセキュリティ構成設定を適用する]** を選択し、  **[Windows Server]** を選択してから、**[保存]** を選択します。</li><li>Linux Server エンドポイントは、[Linux でのMicrosoft Defender for Endpointの前提条件を](../defender-endpoint/microsoft-defender-endpoint-linux.md#prerequisites)満たしています。</li></ul> |

> [!NOTE]
> [Azure Active Directory (Azure AD)](/azure/active-directory/fundamentals/active-directory-whatis) は、ユーザーのアクセス許可とデバイス グループを管理するために使用されます。 Azure AD は Defender for Business サブスクリプションに含まれています。 
> - 試用版を開始する前に Microsoft 365 サブスクリプションがない場合は、アクティブ化プロセス中に Azure AD がプロビジョニングされます。 
> - Defender for Business 試用版を開始するときに別の Microsoft 365 サブスクリプションがある場合は、既存の Azure AD サービスを使用できます。 
> - Defender for Business 試用版を開始するときに[Microsoft 365 Business Premium](../../business/index.yml)を使用している場合は、Intuneを使用してデバイスを管理できます。

## <a name="next-steps"></a>次の手順

[手順 2: Defender for Business でロールとアクセス許可を割り当てるに移動します](mdb-roles-permissions.md)。
 
