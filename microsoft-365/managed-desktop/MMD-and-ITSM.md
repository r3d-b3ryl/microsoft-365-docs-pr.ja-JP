---
title: Microsoft マネージド デスクトップと ITIL (IT インフラストラクチャ ライブラリ)
description: ITIL フェーズと情報と記事Microsoft マネージド デスクトップ関連付ける
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント、ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: ced0b27b5d9a47923b9738a3db50c2a8df0a5cbf
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205763"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft マネージド デスクトップと ITIL (IT インフラストラクチャ ライブラリ)

多くの組織では [、ITIL](https://www.axelos.com/best-practice-solutions/itil)などの正式な IT サービス モデル (ITSM) のラインに沿って IT サービスを構造化する価値があります。 

Microsoft マネージド デスクトップ、組織はこのような正式な ITSM モデルの多くの重要な側面に準拠できます。 ITIL を例として使用すると、この記事では、一般的な ITIL フェーズとプロセス間の接続と、該当する場合は同等Microsoft マネージド デスクトップ機能を確認できます。 この情報は、組織のMicrosoft マネージド デスクトップにのみ適用されます。

ITIL とそのフェーズとプロセスの詳細については、ドキュメントを参照 [してください](https://www.axelos.com/best-practice-solutions/itil)。


## <a name="service-design"></a>サービス設計

次の表は、ITIL の主要なフェーズとプロセスを、Microsoft マネージド デスクトップ機能に関連付け、詳細についてはドキュメントへのリンクを参照してください。



|ITIL プロセス |説明  |ドキュメント |
|---------|---------|---------|
|サービス レベルの管理     | 応答時間は、管理者サポート要求とインシデントに対して定義されます。  |  [Microsoft マネージド デスクトップの管理者サポート](working-with-managed-desktop/admin-support.md)  |
|サービス カタログの管理     | サービスのコンポーネントを詳細に説明するサービスの説明は、現在および関心のあるすべての顧客が利用できるサービスの状態に対応します。<br><br>サービスの運用に必要な情報を理解するために詳しく説明されている前提条件。  | - [Microsoft マネージド デスクトップサービスの説明](service-description/index.md)<br><br>- [ユーザー登録の準備をMicrosoft マネージド デスクトップ](get-ready/index.md)  |
|情報セキュリティ管理     | サービスの情報セキュリティを含むセキュリティ情報。<br><br> セキュリティ関連のポリシーと、デバイスの構成方法に関するその他の情報。   | - [セキュリティのMicrosoft マネージド デスクトップ](service-description/security.md)<br><br>- [デバイス構成](service-description/device-policies.md)  |
|可用性の管理     |  Microsoft マネージド デスクトップの可用性を確保するために、組織と責任のバランスを取る必要があります。<br><br>サービスまたは可用性の問題がある場合、管理者とユーザーはそれぞれのサポートへのルートを持っています。 | - [Microsoft マネージド デスクトップ操作と監視](service-description/operations-and-monitoring.md)<br><br>- [管理者向けサポート Microsoft マネージド デスクトップ](working-with-managed-desktop/admin-support.md)<br>- [ユーザーのヘルプの取得](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>サービス移行


|ITIL プロセス |説明  |ドキュメント |
|---------|---------|---------|
|変更管理     | 利用可能な変更管理に関連する責任、プロセスの概要、および種類の定義されたバランス。  | [Microsoft マネージド デスクトップ操作と監視](service-description/operations-and-monitoring.md#change-management) |
|リリースと展開の管理     |  Microsoft マネージド デスクトップに登録されているデバイスの更新プログラムを管理します。  | [更新プログラムの処理方法は、Microsoft マネージド デスクトップ](service-description/updates.md)        |
|サービス資産と構成管理     | 組織の展開に関する情報Microsoft マネージド デスクトップ IT 管理ポータルで確認できます。  | [Microsoft マネージド デスクトップの管理者サポート](working-with-managed-desktop/admin-support.md) |
|ナレッジ管理     | このサイトではMicrosoft マネージド デスクトップサービスに関する情報が最新の状態に保たれ、   | [Microsoft マネージド デスクトップのドキュメントの変更履歴](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>サービス操作


|ITIL プロセス |説明  |ドキュメント  |
|---------|---------|---------|
|イベント管理     |  デバイスの監視に関する詳細が提供されます。<br><br>サービスの標準操作手順Microsoft マネージド デスクトップ詳細です。 |  - [セキュリティのMicrosoft マネージド デスクトップ](service-description/security.md)<br>- [Microsoft マネージド デスクトップ操作と監視](service-description/operations-and-monitoring.md)       |
|インシデント管理  | Microsoft マネージド デスクトップ定義された重大度定義ごとのインシデントを調査し、処理します。  |  [要求の重大度の定義をサポートする](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|フルフィルメント管理の要求     |  サービスに関連する情報要求および変更要求のプロセスMicrosoft マネージド デスクトップ定義されます。         |[Microsoft マネージド デスクトップの管理者サポート](working-with-managed-desktop/admin-support.md)         |
|問題の管理     | サービスに関する問題は、現時点でローカル アカウント チームに指示する必要があります。 | 開発中のドキュメント |
|アクセス管理     | 機能の詳細を確認するために、お客様の管理コンポーネントと責任にアクセスします。  | [ID およびアクセス管理](service-description/security.md#identity-and-access-management)        |
