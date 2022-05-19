---
title: アクション センターにアクセスして修復アクションを確認する
description: アクション センターを使用して、自動調査の後に詳細と結果を表示する
keywords: action, center, autoir, 自動化, 調査, 応答, 修復
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
ms.technology: mde
ms.openlocfilehash: 6a2cc5d4315c5dd64a852c74176272061789b1ba
ms.sourcegitcommit: e624221597480295b799d56568c4f6f56d40b41d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2022
ms.locfileid: "65535406"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>アクション センターにアクセスして修復アクションを確認する

自動調査中および自動調査後に、脅威検出の修復アクションが識別されます。 特定の脅威と、組織に対する [自動調査と修復機能の構成](configure-automated-investigations-remediation.md) 方法に応じて、一部の修復アクションが自動的に実行され、他のユーザーは承認を必要とします。 組織のセキュリティ運用チームの一員である場合は、**アクション センター** で保留中の修復アクションと完了済み [修復アクション](manage-auto-investigation.md#remediation-actions)を表示できます。

**適用対象:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Business](../defender-business/mdb-overview.md)

## <a name="the-unified-action-center"></a>統合アクション センター

最近、アクション センターが更新されました。 これで、統合されたアクション センター エクスペリエンスが得られます。 アクション センターにアクセスするには、アクセスして [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) サインインします。

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Microsoft 365 Defender ポータルの [アクション センター] ページ" lightbox="images/mde-action-center-unified.png":::

### <a name="whats-changed"></a>何が変更されましたか?

次の表では、新しい統合アクション センターを前のアクション センターと比較します。

|新しい統合アクション センター  |前のアクション センター  |
|---------|---------|
|デバイスと電子メールの保留中のアクションと完了したアクションを 1 つの場所に一覧表示する <br/>([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)プラス[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp))|デバイスの保留中のアクションと完了したアクションの一覧 <br/> ([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)のみ)   |
|は次の場所にあります。<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |は次の場所にあります。<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>で、[**アクション センター**] を選択します。 <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Microsoft 365 Defender ポータルのアクション センターへのナビゲーション ウィンドウ" lightbox="images/action-center-nav-new.png"::: | Microsoft 365 Defender ポータルで、[**自動調査** > **アクション センター**] を選択します。 <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Microsoft 365 Defender ポータルのアクション センターへの以前のバージョンのナビゲーション ウィンドウ" lightbox="images/action-center-nav-old.png":::  |

統合アクション センターは、Defender for Endpoint とDefender for Office 365全体に修復アクションをまとめます。 すべての修復アクションに共通言語を定義し、統合された調査エクスペリエンスを提供します。

適切なアクセス許可と次のサブスクリプションの 1 つ以上を持っている場合は、統合アクション センターを使用できます。

- [Microsoft 365 Defender](/microsoft-365/security/mtp/microsoft-threat-protection)
- [Defender for Endpoint](microsoft-defender-endpoint.md)
- [Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp)
- [Defender for Business](../defender-business/mdb-overview.md)

## <a name="using-the-action-center"></a>アクション センターの使用

強化されたMicrosoft 365 Defender ポータルで統合アクション センターにアクセスするには、

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動し、サインインします。

2. ナビゲーション ウィンドウで、[ **アクション センター**] を選択します。

3. **[保留中のアクション]** タブと [**履歴]** タブを使用します。 次の表は、各タブに表示される内容をまとめたものです。

   |タブ|説明|
   |---|---|
   |**Pending**|注意が必要なアクションの一覧を表示します。 アクションを 1 つずつ承認または拒否したり、同じ種類のアクション ( **検疫ファイル** など) がある場合は複数のアクションを選択したりできます。 <p> **ヒント**: 自動調査を適時に完了できるように、保留中のアクションをできるだけ早く [確認して承認 (または拒否)](manage-auto-investigation.md) してください。|
   |**履歴**|実行されたアクションの監査ログとして機能します。次のようになります。 <ul><li>自動調査の結果として実行された修復アクション</li><li>セキュリティ運用チームによって承認された修復アクション</li><li>実行されたコマンドと、ライブ応答セッション中に適用された修復アクション</li><li>Microsoft Defender ウイルス対策の脅威保護機能によって実行された修復アクション</li></ul> <p> 特定のアクションを元に戻す方法を提供します ( [完了したアクションを元に戻すを](manage-auto-investigation.md#undo-completed-actions)参照)。|

4. アクション センターでデータをカスタマイズ、並べ替え、フィルター処理、エクスポートするには、次の手順のうち 1 つ以上を実行します。

   :::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="列とフィルターを含むアクション センター" lightbox="images/new-action-center-columnsfilters.png":::

   - 昇順または降順で項目を並べ替える列見出しを選択します。
   - 期間フィルターを使用して、過去の日、週、30 日間、または 6 か月間のデータを表示します。
   - 表示する列を選択します。
   - データの各ページに含める項目の数を指定します。
   - フィルターを使用して、表示するアイテムのみを表示します。
   - [ **エクスポート]** を選択して、結果を.csv ファイルにエクスポートします。

## <a name="next-steps"></a>次の手順

- [修復アクションを表示および承認する](manage-auto-investigation.md)
- [対話型ガイドを参照してください:Microsoft Defender for Endpointを使用して脅威を調査して修復する](https://aka.ms/MDATP-IR-Interactive-Guide)

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Endpoint での誤検出/検出漏れに対処する](defender-endpoint-false-positives-negatives.md)
- [中小企業向けのMicrosoft 365プランのセキュリティ機能を比較する](../defender-business/compare-mdb-m365-plans.md)
