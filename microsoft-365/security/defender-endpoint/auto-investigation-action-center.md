---
title: アクション センターにアクセスして修復アクションを確認する
description: アクション センターを使用して、自動調査後の詳細と結果を表示する
keywords: action, center, autoir, 自動, 調査, 応答, 修復
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: 7c300a6d66ae67d481b61a0a35101a0472031266
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327687"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>アクション センターにアクセスして修復アクションを確認する

自動調査中および自動調査後に、脅威検出に対する修復アクションが識別されます。 特定の脅威と [Microsoft Defender for Endpoint](/windows/security/threat-protection) の組織の構成方法に応じて、一部の修復アクションが自動的に実行され、承認が必要な修復アクションもあります。 組織のセキュリティ運用チームの一員である場合は、アクション センターで保留中の修復アクションと完了済 [](manage-auto-investigation.md#remediation-actions)み修復アクションを **表示できます**。


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a>(NEW!)統合アクション センター


新しい統合アクション センター ()をお知らせ[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)します。

:::image type="content" source="images/mde-action-center-unified.png" alt-text="ポータルのアクション センター Microsoft 365 Defenderします。":::

次の表は、新しい統合アクション センターと前のアクション センターを比較します。

|統合された新しいアクション センター  |前のアクション センター  |
|---------|---------|
|デバイスと電子メールの保留中のアクションと完了したアクションを 1 つの場所に一覧表示する <br/>([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) plus [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp))|デバイスの保留中のアクションと完了したアクションの一覧 <br/> ([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) のみ)   |
|場所は次の場所です。<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |場所は次の場所です。<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| [ポータル] <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender、[</a>アクション センター] **を選択します**。 <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="ポータルでアクション センターに移動Microsoft 365 Defenderします。"::: | [自動調査Microsoft 365 Defender] ポータルで、[**自動調査** > **] アクション センターを選択します**。 <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="ポータルからアクション センターに移動Microsoft 365 Defenderします。":::  |

統合アクション センターでは、エンドポイント用の Defender と Defender をまたがった修復アクションOffice 365。 すべての修復アクションの共通言語を定義し、統合された調査エクスペリエンスを提供します。

適切なアクセス許可と次のサブスクリプションの 1 つ以上がある場合は、統合アクション センターを使用できます。

- [Defender for Endpoint](microsoft-defender-endpoint.md)
- [Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp)
- [Microsoft 365 Defender](/microsoft-365/security/mtp/microsoft-threat-protection)

> [!TIP]
> 詳細については、「要件」 [を参照してください](/microsoft-365/security/mtp/prerequisites)。

## <a name="using-the-action-center"></a>アクション センターの使用

改善されたポータルで統合アクション センターにアクセスするには、次Microsoft 365 Defenderします。

1. ポータルに移動<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderサインイン</a>します。
2. ナビゲーション ウィンドウで、[アクション センター] **を選択します**。

アクション センターにアクセスすると、[保留中のアクション] と [履歴] **の 2 つのタブ** が **表示されます**。 次の表に、各タブに表示される内容の概要を示します。

|タブ|説明|
|---|---|
|**Pending**|注意が必要なアクションの一覧を表示します。 アクションを一度に 1 つ承認または拒否するか、同じ種類のアクション (検疫ファイルなど) がある場合は複数のアクション **を選択できます**。 <p> **ヒント**: 自動化された調査が、時間に合った方法で完了するように、保留中のアクションをできるだけ早く確認して承認 (または拒否 [)](manage-auto-investigation.md) してください。|
|**履歴**|次のようなアクションの監査ログとして機能します。 <ul><li>自動調査の結果として実行された修復アクション</li><li>セキュリティ運用チームによって承認された修復アクション</li><li>Live Response セッション中に適用された、実行されたコマンドと修復アクション</li><li>脅威保護機能によって実行された修復Microsoft Defender ウイルス対策</li></ul> <p> 特定のアクションを元に戻す方法を提供します (「完了した操作を元に戻[す」を参照)。](manage-auto-investigation.md#undo-completed-actions)|

アクション センターでデータをカスタマイズ、並べ替え、フィルター処理、およびエクスポートできます。

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="アクション センターの列とフィルター。":::

- 列見出しを選択して、アイテムを昇順または降順に並べ替えます。
- 期間フィルターを使用して、過去の日、週、30 日、または 6 か月のデータを表示します。
- 表示する列を選択します。
- データの各ページに含めるアイテムの数を指定します。
- フィルターを使用して、表示するアイテムを表示します。
- [エクスポート **] を** 選択して、結果を.csvします。

## <a name="next-steps"></a>次の手順

- [修復アクションを表示および承認する](manage-auto-investigation.md)
- [対話型ガイドを参照してください。 Microsoft Defender for Endpoint を使用して脅威を調査して修復する](https://aka.ms/MDATP-IR-Interactive-Guide)

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Endpoint での誤検出/検出漏れに対処する](defender-endpoint-false-positives-negatives.md)
