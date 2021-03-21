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

Microsoft Managed Desktop には、組織内の IT 管理者がデバイスの人口のさまざまな側面を理解するために使用できるいくつかのレポートとダッシュボードが提供されています。レポートは [、Microsoft Endpoint Manager](https://endpoint.microsoft.com) と Microsoft 365 管理センターの [2 つの場所にあります](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)。 

## <a name="reports-in-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager のレポート

Microsoft Endpoint Manager コンソールでは、複数の製品からのレポートを 1 つの場所にまとめ、Azure AD 組織 ("tenant") の構成とデバイスに関する問題の監視と調査に役立ちます。 Microsoft Managed desktop には、メイン メニューの [レポート] の下に、登録したデバイスの Microsoft Managed Desktop の管理に固有のレポートを見つけるセクションがあります。

これらのレポートには、次のものが含まれます。
- **管理対象デバイス**  > **機能更新** プログラム : このビューには、Microsoft Managed Desktop デバイス全体の機能更新プログラムの全体的な状態が表示されます。
- **管理対象デバイス**  > **Office更新プログラム**: このビューには、Microsoft Managed Desktop デバイスOffice更新プログラムの全体的な状態が表示されます。

さらに、Microsoft Endpoint Manager の複数の場所で、他の製品グループからレポートをフィルター処理して、Microsoft Managed Desktop で管理されているデバイスを具体的に含めるか除外することもできます。 これらのレポートには、次のフィルター機能が統合されています。

- [すべてのデバイス](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [デバイスのポリシー準拠](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [非準拠デバイス](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Microsoft Managed Desktop のカスタム ロールは、Microsoft Managed Desktop レポートへのアクセスのみを保証します。 すべてのデバイスなど、Microsoft Endpoint Manager の他の部分にアクセスするには、「Microsoft Intune を使用した役割ベースのアクセス[制御」を参照してください](/mem/intune/fundamentals/role-based-access-control)。 

## <a name="reports-in-microsoft-365-admin-center"></a>Microsoft 365 管理センターのレポート

Microsoft Managed Desktop インサイト レポートを見つけるには [、Microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)管理センターを開き、[レポート] に移動して **[Microsoft Managed Desktop] を選択します**。 これらのレポートへの直接リンクは、ホームページの Microsoft Endpoint Manager の **[Microsoft Managed Desktop]** タブ [からフォローすることもできます](https://endpoint.microsoft.com)。 

これらのレポートには、次のものが含まれます。 

- [利用状況の分析](usage-insights.md) 情報 - このビューでは、Microsoft Managed Desktop デバイスの使用状況の指標を提供します。
- [信頼性の分析情報](reliability-insights.md) - このビューには、管理対象デバイスの正常性の概要が表示されます。
- [バッテリーの分析](battery-insights.md) 情報 - このビューには、環境内のデバイスのアプリのエネルギー消費量と、投影されるバッテリ寿命に関する情報が表示されます。
- [Windows セキュリティ更新プログラムの分析](security-update-insights.md) 情報 - このビューには、Microsoft Managed Desktop デバイスのセキュリティ更新プログラムの状態に関する情報が表示されます。

 ## <a name="inventory-data"></a>インベントリ データ

他のレポートに加えて、Microsoft Managed Desktop によって管理されるデバイスに関する情報をエクスポートできます。 Microsoft Endpoint Manager **の [** デバイス]**領域の**  [デバイス] ビューで、[すべてエクスポート] タブを使用して詳細なインベントリ レポート [をダウンロードします](device-inventory-report.md)。