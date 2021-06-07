---
title: レポートを操作する
description: このサイトで使用できるさまざまなレポートMicrosoft マネージド デスクトップ
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b37ce09a0781aa83970502224ddbb3658ed07d69
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771887"
---
# <a name="work-with-reports"></a>レポートを操作する

Microsoft マネージド デスクトップ、組織の IT 管理者がデバイスの人口のさまざまな側面を理解するために使用できるいくつかのレポートとダッシュボードを提供します。 

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

## <a name="endpoint-analytics"></a>エンドポイント分析
Microsoft マネージド デスクトップエンドポイント分析と[統合されました](/mem/analytics/overview)。 これらのレポートは、組織の動作状況とユーザーに提供されるエクスペリエンスの品質を測定するための分析情報を提供します。 エンドポイント分析は、エンドポイントの **[レポート**] メニュー [Microsoft エンドポイント マネージャー。](https://endpoint.microsoft.com/) スコアをピボットして、任意のレポートに移動Microsoft マネージド デスクトップ管理されているデバイスのみを含めるには、[フィルター]ドロップダウンを選択し、[デバイス] **Microsoft マネージド デスクトップします**。

登録中に Azure AD組織 ("tenant") に対してエンドポイント分析が自動的に構成されていない場合は、自分で行います。 詳細については [、「Onboard in the Endpoint analytics portal」を参照してください](/mem/analytics/enroll-intune#bkmk_onboard)。 すべてのデバイスを登録するか、Microsoft マネージド デスクトップ デバイスのみを含める場合は、テスト、First、Fast、およびBroad のモダン ワークプレース デバイス グループを選択します。 これらのレポートでは、さまざまなアクセス許可が必要になる場合があります。 詳細については、「アクセス許可」 [を参照](/mem/analytics/overview#permissions) して、役割が適切に割り当てられているか確認してください。

> [!NOTE]
> プライバシー ユーザーのプライバシーを尊重するために、このフィルターを使用するには、Endpoint analytics に登録Microsoft マネージド デスクトップデバイスが 10 台を超える必要があります。

 ## <a name="inventory-data"></a>インベントリ データ

他のレポートに加えて、ユーザーが管理するデバイスに関する情報をエクスポートMicrosoft マネージド デスクトップ。 [すべての **デバイス]** タブの [デバイス] Microsoft エンドポイント マネージャーで、[すべてエクスポート] タブを使用して詳細なインベントリ レポート [をダウンロードします](device-inventory-report.md)。
