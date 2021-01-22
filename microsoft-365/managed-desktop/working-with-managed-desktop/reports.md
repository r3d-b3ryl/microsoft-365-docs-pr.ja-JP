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
ms.openlocfilehash: a80616b58298ba544b9eab1d19ffb77f0e6825d4
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921352"
---
# <a name="work-with-reports"></a>レポートを操作する

Microsoft マネージド デスクトップには、組織内の IT 管理者がデバイスの多様な側面を理解するために使用できる、いくつかのレポートとダッシュボードがあります。レポートは [、Microsoft Endpoint Manager](https://endpoint.microsoft.com) と [Microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)管理センターの 2 つの場所にあります。 

## <a name="reports-in-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager のレポート

Microsoft Endpoint Manager コンソールは、複数の製品からのレポートを 1 つの場所にまとめ、Azure AD 組織 ("テナント") の構成とデバイスに関する問題の監視と調査に役立ちます。 Microsoft マネージド デスクトップには、メインメニューの [レポート] の下にセクションがあります。このセクションでは、登録したデバイスの Microsoft マネージド デスクトップの管理に固有のレポートを見つけられます。

これらのレポートには、次のものが含まれます。
- **管理対象デバイス**  > **機能更新** プログラム : このビューには、Microsoft マネージド デスクトップ デバイス全体の機能更新プログラムの全体的な状態が表示されます。
- **管理対象デバイス**  > **Office更新**: このビューには、Microsoft マネージド デスクトップ デバイスOffice更新プログラムの全体的な状態が表示されます。

さらに、Microsoft Endpoint Manager の複数の場所では、他の製品グループからのレポートをフィルター処理して、Microsoft マネージド デスクトップで管理されているデバイスを具体的に含めるか除外することができます。 これらのレポートには、次のフィルタリング機能が統合されています。

- [すべてのデバイス](https://docs.microsoft.com/mem/intune/remote-actions/device-management#get-to-your-devices)
- [デバイスのポリシー準拠](https://docs.microsoft.com/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [準拠しないデバイス](https://docs.microsoft.com/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> カスタムの Microsoft マネージド デスクトップの役割は、Microsoft マネージド デスクトップ レポートへのアクセスのみを保証します。 すべてのデバイスなど、Microsoft Endpoint Manager の他の部分にアクセスするには、Microsoft Intune による役割ベースのアクセス[制御を参照してください](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)。 

## <a name="reports-in-microsoft-365-admin-center"></a>Microsoft 365 管理センターのレポート

Microsoft Managed Desktop Insights レポートを見つけるには [、Microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)管理センターを開き、[レポート] に移動して [Microsoft マネージド デスクトップ]**を選択します**。 これらのレポートへの直接リンクは、ホーム ページの Microsoft Endpoint Manager の **[Microsoft マネージド** デスクトップ] [タブから実行することもできます](https://endpoint.microsoft.com)。 

これらのレポートには、次のものが含まれます。 

- [利用状況の分析](usage-insights.md) 情報 - このビューは、Microsoft マネージド デスクトップ デバイスの使用状況の指標を提供します。
- [信頼性の分析](reliability-insights.md) 情報 - このビューには、管理対象デバイスの正常性の概要が表示されます。
- [バッテリーの分析](battery-insights.md) 情報 - このビューには、環境内のデバイスに対するアプリの電力消費量と、バッテリー残量の計画に関する情報が表示されます。
- [Windows セキュリティ更新プログラムの分析](security-update-insights.md) 情報 - このビューには、Microsoft マネージド デスクトップ デバイスのセキュリティ更新プログラムの状態に関する情報が表示されます。

 ## <a name="inventory-data"></a>インベントリ データ

その他のレポートに加えて、Microsoft マネージド デスクトップで管理されているデバイスに関する情報をエクスポートできます。 Microsoft Endpoint Manager **の [** デバイス] 領域の[デバイス] ビューで、[すべてエクスポート] タブを使用して、詳細なインベントリ レポート [をダウンロードします](device-inventory-report.md)。
