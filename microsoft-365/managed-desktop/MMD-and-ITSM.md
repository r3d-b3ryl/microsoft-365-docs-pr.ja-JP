---
title: Microsoft マネージド デスクトップと ITIL (IT インフラストラクチャ ライブラリ)
description: ''
keywords: Microsoft Managed Desktop、Microsoft 365、service、documentation、ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 4b735ec28b655dfc01c874bc4865388d11247b67
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47947962"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft マネージド デスクトップと ITIL (IT インフラストラクチャ ライブラリ)

多くの組織では、 [ITIL](https://www.axelos.com/best-practice-solutions/itil)などの形式化された It サービスモデル (ITSM) の行に沿って it サービスを構造化することが重要です。 

Microsoft マネージドデスクトップを使用すると、組織は、このような形式化された ITSM モデルの多くの重要な側面に準拠できます。 このトピックでは、ITIL を例として使用して、一般的な ITIL フェーズとプロセスの間の接続、および該当する場合には Microsoft マネージドデスクトップの同等の機能を確認することができます。 これは、組織の Microsoft マネージドデスクトップ部分にのみ適用されます。

ITIL およびそのフェーズとプロセスの詳細については、 [ドキュメント](https://www.axelos.com/best-practice-solutions/itil)を参照してください。


## <a name="service-design"></a>サービス設計

この表では、主要な ITIL のフェーズとプロセスを Microsoft 管理デスクトップ機能に関連付け、詳細についてはドキュメントへのリンクを示します。



|ITIL プロセス |Description  |ドキュメント |
|---------|---------|---------|
|サービスレベルの管理     | 応答時間は、管理者サポート要求とインシデントに対して定義されます。  |  [Microsoft マネージド デスクトップの管理者サポート](working-with-managed-desktop/admin-support.md)  |
|サービスカタログの管理     | サービスの説明サービスの各コンポーネントの詳細については、「サービスの状態」を参照してください。<br><br>サービスを運用するために必要なことを理解するために詳細な前提条件。  | - [Microsoft マネージドデスクトップサービスの説明](service-description/index.md)<br><br>- [Microsoft マネージドデスクトップでの登録準備をする](get-ready/index.md)  |
|情報セキュリティの管理     | セキュリティ情報。サービスの情報セキュリティを含みます。<br><br> セキュリティ関連のポリシーと、デバイスの構成方法に関するその他の情報。   | - [Microsoft マネージドデスクトップのセキュリティ](service-description/security.md)<br><br>- [デバイス構成](service-description/device-policies.md)  |
|可用性管理     |  Microsoft マネージドデスクトップは、サービスの可用性を確保するために、組織とのバランスをとります。<br><br>管理者とユーザーは、サービスまたは可用性の問題が発生した場合に、それぞれのサポートにルーティングされます。 | - [Microsoft マネージドデスクトップの操作と監視](service-description/operations-and-monitoring.md)<br><br>- [Microsoft マネージドデスクトップの管理者サポート](working-with-managed-desktop/admin-support.md)<br>- [ユーザーのヘルプを取得する](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>サービス移行


|ITIL プロセス |Description  |ドキュメント |
|---------|---------|---------|
|変更管理     | 定義されている責任のバランス、プロセスの概要、および変更管理に関連する種類。  | [Microsoft マネージドデスクトップの操作と監視](service-description/operations-and-monitoring.md#change-management) |
|リリースと展開の管理     |  Microsoft マネージドデスクトップは、サービスに登録されたデバイスの更新プログラムを管理します。  | [Microsoft マネージドデスクトップでの更新プログラムの処理方法](service-description/updates.md)        |
|サービスの資産と構成の管理     | 組織の Microsoft Managed Desktop の展開に関する情報は、IT 管理ポータルで参照できます。  | [Microsoft マネージド デスクトップの管理者サポート](working-with-managed-desktop/admin-support.md) |
|ナレッジ管理     | Microsoft マネージドデスクトップサービスの情報は、このサイトで最新の状態に保たれます。   | [Microsoft マネージド デスクトップのドキュメントの変更履歴](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>サービス操作


|ITIL プロセス |Description  |ドキュメント  |
|---------|---------|---------|
|イベントの管理     |  デバイスの監視の詳細について説明します。<br><br>Microsoft マネージドデスクトップサービスの標準的な運用手順について説明します。 |  - [Microsoft マネージドデスクトップのセキュリティ](service-description/security.md)<br>- [Microsoft マネージドデスクトップの操作と監視](service-description/operations-and-monitoring.md)       |
|インシデント管理  | Microsoft マネージドデスクトップは、定義された重要度定義ごとにインシデントを調査して処理します。  |  [サポート要求の重要度の定義](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|要求フルフィルメントの管理     |  Microsoft Managed Desktop service に関連する情報および変更要求の要求の処理が定義されています。         |[Microsoft マネージド デスクトップの管理者サポート](working-with-managed-desktop/admin-support.md)         |
|問題の管理     | サービスに関する問題は、この時点でローカルアカウントチームに送られる必要があります。 | 開発に関するドキュメント |
|アクセス管理     | お客様の管理コンポーネントと責任にアクセスして、機能が詳細になるようにします。  | [ID およびアクセス管理](service-description/security.md#identity-and-access-management)        |
