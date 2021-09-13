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
ms.openlocfilehash: 2a28112c8afe9165453153d2d23752325ae2e6d8
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215153"
---
# <a name="work-with-reports"></a>レポートを操作する

Microsoft エンドポイント マネージャー コンソールでは、複数の製品からのレポートを 1 つの場所にまとめ、Azure AD 組織 ("tenant") の構成とデバイスに関する問題の監視と調査に役立ちます。 Microsoft Managed desktop には、[レポート] メニューのセクションがあります。このセクションでは、登録したMicrosoft マネージド デスクトップの管理に固有のレポートを見つけられます。 さらに、Microsoft エンドポイント マネージャー を通じて複数の場所で、他の製品グループからレポートをフィルター処理して、ユーザーが管理するデバイスを具体的に含めるか除外Microsoft マネージド デスクトップ。 

## <a name="microsoft-managed-desktop-reports"></a>Microsoft マネージド デスクトップレポート
Microsoft マネージド デスクトップ、組織の IT 管理者がデバイスの人口のさまざまな側面を理解するために使用できるいくつかのレポートとダッシュボードを提供します。これらのレポートを見つけるには、デバイスの [レポート]メニューの [Microsoft マネージド デスクトップ]セクションにある [管理対象デバイス] に移動Microsoft エンドポイント マネージャー。  

[概要 **] タブ** には、デバイスの更新に関する簡単な指標が表示されます。 [メトリック **の詳細を表示** する] を選択すると、メトリックの基になるデータセットなど、オフライン分析の追加情報をダウンロードできます。

[レポート] タブ **を選択** すると、使用可能な詳細レポートの説明が表示されます。 これらのレポートは、より包括的で、ポータル内のデータの視覚化とフィルター処理、およびオフライン分析または配布用の基になるデータのエクスポートをサポートします。 現在、次のレポートを利用できます。
- [[**デバイスの状態]** レポート](device-status-report.md)(*プレビュー*) には、デバイスのアクティビティと使用状況に基Microsoft マネージド デスクトップサービスの使用が表示されます。 
- デバイスの状態 **の傾向***(プレビュー*) を使用して、デバイスの過去 60 日間のデバイスの状態の傾向をMicrosoft マネージド デスクトップできます。 傾向は、デバイスの状態を、新しい展開など、時間の間に他の変更と関連付けるのに役立ちます。 
- [ **[Windowsセキュリティ更新プログラム]** レポート](security-updates-report.md)*(プレビュー*) には、Windowsデバイス間でセキュリティ更新プログラムがMicrosoft マネージド デスクトップされます。


## <a name="endpoint-analytics"></a>エンドポイント分析
Microsoft マネージド デスクトップエンドポイント分析と[統合されました](/mem/analytics/overview)。 これらのレポートは、組織の動作状況とユーザーに提供されるエクスペリエンスの品質を測定するための分析情報を提供します。 エンドポイント分析は、エンドポイントの **[レポート**] メニュー [Microsoft エンドポイント マネージャー。](https://endpoint.microsoft.com/) スコアをピボットして、任意のレポートに移動Microsoft マネージド デスクトップ管理されているデバイスのみを含めるには、[フィルター]ドロップダウンを選択し、[デバイス] **Microsoft マネージド デスクトップします**。

登録中に Azure AD組織 ("tenant") に対してエンドポイント分析が自動的に構成されていない場合は、自分で行います。 詳細については [、「Onboard in the Endpoint analytics portal」を参照してください](/mem/analytics/enroll-intune#bkmk_onboard)。 すべてのデバイスを登録するか、Microsoft マネージド デスクトップ デバイスのみを含める場合は、Test、First、Fast、およびBroad のモダン ワークプレース デバイス グループを選択します。 これらのレポートでは、さまざまなアクセス許可が必要になる場合があります。 詳細については、「アクセス許可」 [を参照](/mem/analytics/overview#permissions) して、役割が適切に割り当てられているか確認してください。

> [!NOTE]
> ユーザーのプライバシーを尊重するために、このフィルターを使用するには、Endpoint analytics に登録Microsoft マネージド デスクトップデバイスが 10 台を超える必要があります。

## <a name="intune-reports"></a>Intune レポート
Microsoft Intuneは、お客様に代わってデバイスを管理するために使用するサービスの 1 つです。 場合によっては、Intune レポートを使用して、デバイスの管理を具体的に監視Microsoft マネージド デスクトップがあります。 または、他のデバイスの管理に使用するレポートから、管理するデバイスを除外することもできます。 次のレポートでは、デバイスを含めるか除外する機能Microsoft マネージド デスクトップできます。

- [すべてのデバイス](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [デバイスのポリシー準拠](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [非準拠デバイス](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> カスタム Microsoft マネージド デスクトップロールは、レポートへのアクセスのみをMicrosoft マネージド デスクトップします。 すべてのデバイスなど、Microsoft エンドポイント マネージャーの他の部分にアクセスするには、「すべてのデバイスを使用した役割ベースのアクセス[制御」をMicrosoft Intune。](/mem/intune/fundamentals/role-based-access-control) 

## <a name="microsoft-managed-desktop-inventory-data"></a>Microsoft マネージド デスクトップデータの取得

他のレポートに加えて、ユーザーが管理するデバイスに関する情報をエクスポートMicrosoft マネージド デスクトップ。 [すべての **デバイス]** タブの [デバイス] Microsoft エンドポイント マネージャーで、[すべてエクスポート] タブを使用して詳細なインベントリ レポート [をダウンロードします](device-inventory-report.md)。
