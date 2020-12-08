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
ms.openlocfilehash: bfd8305d23e0e6d761c629ee3048c6204f702d37
ms.sourcegitcommit: 98146c67a1d99db5510fa130340d3b7be8d81b21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2020
ms.locfileid: "49585330"
---
# <a name="work-with-reports"></a>レポートを操作する

Microsoft マネージドデスクトップには、組織内の管理者が、デバイスの作成に関するさまざまな側面を理解するために使用できる、いくつかのレポートとダッシュボードが用意されています。レポートについては、「 [Microsoft エンドポイントマネージャー](https://endpoint.microsoft.com) 」および「 [Microsoft 365 管理センター](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)」の2つの場所にあります。 

## <a name="reports-in-microsoft-endpoint-manager"></a>Microsoft エンドポイントマネージャーのレポート

Microsoft エンドポイントマネージャーコンソールは、複数の製品からのレポートを1つの場所にまとめて、Azure AD 組織 ("テナント") の構成とデバイスに関する問題を監視し、調査するために役立ちます。 Microsoft マネージドデスクトップには、メインメニューの [ **レポート** ] の下にセクションがあります。ここでは、登録されているデバイスを Microsoft managed desktop で管理するためのレポートについて説明します。

さらに、Microsoft エンドポイントマネージャー全体のいくつかの場所では、他の製品グループからのレポートをフィルター処理して、Microsoft マネージドデスクトップで管理されるデバイスを具体的に含めたり除外したりできます。 これらのレポートは、次のフィルター処理機能を統合しています。

- **すべてのデバイス**
- **デバイスのポリシー準拠**
- **準拠していないデバイス**

> [!NOTE]
> Microsoft Managed Desktop のカスタムの役割では、Microsoft マネージドデスクトップのレポートへのアクセスのみが保証されます。 Microsoft エンドポイントマネージャーの他の部分 (すべての **デバイス** など) にアクセスするには、「 [microsoft Intune での役割ベースのアクセス制御](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)」を参照してください。 

## <a name="reports-in-microsoft-365-admin-center"></a>Microsoft 365 管理センターのレポート

Microsoft Managed Desktop insights レポートを見つけるには、 [microsoft 365 管理センター](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)を開き、[ **レポート** ] に移動して、[ **microsoft managed desktop**] を選択します。 また、これらのレポートへの直接リンクは、ホームページの [Microsoft エンドポイントマネージャー](https://endpoint.microsoft.com)の [ **microsoft Managed Desktop** ] タブからもたどることができます。 

これらのレポートには次のものがあります。 

- [Usage insights](usage-insights.md) -このビューでは、Microsoft マネージドデスクトップデバイスの利用状況メトリックが提供されます。
- [リライアビリティ insights](reliability-insights.md) -管理対象デバイスの正常性の概要を表示します。
- [[バッテリインサイト](battery-insights.md)]-このビューには、環境内のデバイスのアプリケーションの電力消費量および予想されるバッテリ寿命に関する情報が表示されます。
- [Windows セキュリティ更新プログラムインサイト](security-update-insights.md) -このビューには、Microsoft マネージドデスクトップデバイスのセキュリティ更新プログラムの状態に関する情報が表示されます。

 ## <a name="inventory-data"></a>インベントリデータ

他のレポートに加えて、Microsoft マネージドデスクトップで管理されているデバイスに関する情報をエクスポートすることもできます。 Microsoft エンドポイントマネージャーの [**デバイス**] 領域の [**デバイス**] ビューで、[**すべてをエクスポート**] タブを使用して、[詳細なインベントリレポートをダウンロード](device-inventory-report.md)します。