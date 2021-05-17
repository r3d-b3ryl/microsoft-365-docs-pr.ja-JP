---
title: レポートを操作する
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e509ae63225362613962cd0c366c51239f3d4493
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917684"
---
# <a name="work-with-reports"></a>レポートを操作する

Microsoft マネージド デスクトップ、組織の IT 管理者がデバイスの人口のさまざまな側面を理解するために使用できるいくつかのレポートとダッシュボードを提供します。レポートは、次の 2 つの場所[](https://endpoint.microsoft.com)にあります。Microsoft エンドポイント マネージャー管理センター Microsoft 365[表示されます](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)。 

## <a name="reports-in-microsoft-endpoint-manager"></a>[レポート] Microsoft エンドポイント マネージャー

Microsoft エンドポイント マネージャー コンソールでは、複数の製品からのレポートを 1 つの場所にまとめ、Azure AD 組織 ("tenant") の構成とデバイスに関する問題の監視と調査に役立ちます。 Microsoft Managed desktop には、メイン メニューの [レポート] の下に、登録したデバイスの Microsoft マネージド デスクトップの管理に固有のレポートを見つけるセクションがあります。

これらのレポートには、次のものが含まれます。
- **管理対象デバイス**  > **機能更新** プログラム : このビューには、デバイス全体の機能更新プログラムのMicrosoft マネージド デスクトップ表示されます。
- **管理対象デバイス**  > **Office更新** プログラム : このビューには、デバイス全体のOffice更新プログラムのMicrosoft マネージド デスクトップ表示されます。

さらに、Microsoft エンドポイント マネージャー を通じて複数の場所で、他の製品グループからレポートをフィルター処理して、ユーザーが管理するデバイスを具体的に含めるか除外Microsoft マネージド デスクトップ。 これらのレポートには、次のフィルター機能が統合されています。

- [すべてのデバイス](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [デバイスのポリシー準拠](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [非準拠デバイス](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> カスタム Microsoft マネージド デスクトップロールは、レポートへのアクセスのみをMicrosoft マネージド デスクトップします。 すべてのデバイスなど、Microsoft エンドポイント マネージャーの他の部分にアクセスするには、「すべてのデバイスを使用した役割ベースのアクセス[制御」をMicrosoft Intune。](/mem/intune/fundamentals/role-based-access-control) 

## <a name="reports-in-microsoft-365-admin-center"></a>管理センター Microsoft 365レポート

分析情報レポートMicrosoft マネージド デスクトップ見つけるには、管理センターを開Microsoft 365[レポート] に移動し、[レポート] を選択 **Microsoft マネージド デスクトップ。** [](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop) これらのレポートへの直接リンクは、ホームページの **[Microsoft マネージド デスクトップ]** タブ [からMicrosoft エンドポイント マネージャー。](https://endpoint.microsoft.com) 

これらのレポートには、次のものが含まれます。 

- [利用状況の分析](usage-insights.md)情報 - このビューは、ユーザーのデバイスの使用状況Microsoft マネージド デスクトップします。
- [信頼性の分析情報](reliability-insights.md) - このビューには、管理対象デバイスの正常性の概要が表示されます。
- [バッテリーの分析](battery-insights.md) 情報 - このビューには、環境内のデバイスのアプリのエネルギー消費量と、投影されるバッテリ寿命に関する情報が表示されます。
- [Windows更新プログラムの分析](security-update-insights.md)情報 - このビューには、デバイスのセキュリティ更新プログラムの状態に関するMicrosoft マネージド デスクトップ表示されます。

 ## <a name="inventory-data"></a>インベントリ データ

他のレポートに加えて、ユーザーが管理するデバイスに関する情報をエクスポートMicrosoft マネージド デスクトップ。 [すべての **デバイス]** タブの [デバイス] Microsoft エンドポイント マネージャーで、[すべてエクスポート] タブを使用して詳細なインベントリ レポート [をダウンロードします](device-inventory-report.md)。