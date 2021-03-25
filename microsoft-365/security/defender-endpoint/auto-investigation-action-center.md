---
title: アクション センターにアクセスして修復アクションを確認する
description: アクション センターを使用して、自動調査後の詳細と結果を表示する
keywords: action, center, autoir, 自動, 調査, 応答, 修復
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: af9e9315088a8dd5da9740b33135551d28664ed7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186115"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>アクション センターにアクセスして修復アクションを確認する

自動調査中および自動調査後に、脅威検出に対する修復アクションが識別されます。 特定の脅威と [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) の組織の構成方法に応じて、一部の修復アクションが自動的に実行され、承認が必要な修復アクションもあります。 組織のセキュリティ運用チームの一員である場合は、アクション センターで保留中の修復アクションと完了 [](manage-auto-investigation.md#remediation-actions)済み修復アクションを **表示できます**。 


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a>(NEW!)統合アクション センター


新しい統合アクション センター ( )を発表します [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 。

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Microsoft 365 セキュリティ センターのアクション センター":::

次の表は、新しい統合アクション センターと前のアクション センターを比較します。

|統合された新しいアクション センター  |前のアクション センター  |
|---------|---------|
|デバイスと電子メールの保留中のアクションと完了したアクションを 1 つの場所に一覧表示する <br/>([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) plus Microsoft Defender for Office [365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp))|デバイスの保留中のアクションと完了したアクションの一覧 <br/> ([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) のみ)   |
|場所は次の場所です。<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |場所は次の場所です。<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| Microsoft 365 セキュリティ センターで、[アクション センター] **を選択します**。 <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Microsoft 365 セキュリティ センターのアクション センターへの移動"::: | Microsoft Defender セキュリティ センターで、[自動調査 **] アクション センター**  >  **を選択します**。 <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Microsoft Defender セキュリティ センターからアクション センターに移動する":::  |

統合アクション センターでは、365 用の Defender for Endpoint と Defender 全体で修復Officeされます。 すべての修復アクションの共通言語を定義し、統合された調査エクスペリエンスを提供します。 

適切なアクセス許可と次のサブスクリプションの 1 つ以上がある場合は、統合アクション センターを使用できます。
- [Defender for Endpoint](microsoft-defender-endpoint.md)
- [Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp)
- [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> 詳細については、「要件」 [を参照してください](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)。

## <a name="using-the-action-center"></a>アクション センターの使用

強化された Microsoft 365 セキュリティ センターで統合アクション センターにアクセスするには、次の操作を行います。
1. Microsoft 365 セキュリティ センター ( ) に移動し [https://security.microsoft.com](https://security.microsoft.com) 、サインインします。
2. ナビゲーション ウィンドウで、[アクション センター] **を選択します**。 

アクション センターにアクセスすると、[保留中のアクション] と [履歴] **の 2 つのタブ** が **表示されます**。 次の表に、各タブに表示される内容の概要を示します。

|タブ  |説明  |
|---------|---------|
|**Pending**     | 注意が必要なアクションの一覧を表示します。 アクションを一度に 1 つ承認または拒否するか、同じ種類のアクション (検疫ファイルなど) がある場合は複数のアクション **を選択できます**。 <br/>**ヒント**: 保留中のアクションをできるだけ早く確認し、承認 (または拒否 [)](manage-auto-investigation.md) して、自動調査が正時に完了するようにします。 |
|**履歴**     | 次のようなアクションの監査ログとして機能します。 <br/>- 自動調査の結果として実行された修復アクション <br>- セキュリティ運用チームによって承認された修復アクション  <br/>- Live Response セッション中に適用された、実行されたコマンドと修復アクション  <br/>- Microsoft Defender ウイルス対策の脅威保護機能によって実行された修復アクション  <p>特定のアクションを元に戻す方法を提供します (「完了した操作を元に戻[す」を参照)。](manage-auto-investigation.md#undo-completed-actions)       |

アクション センターでデータをカスタマイズ、並べ替え、フィルター処理、およびエクスポートできます。

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="アクション センターの列とフィルター":::

- 列見出しを選択して、アイテムを昇順または降順に並べ替えます。
- 期間フィルターを使用して、過去の日、週、30 日、または 6 か月のデータを表示します。
- 表示する列を選択します。
- データの各ページに含めるアイテムの数を指定します。
- フィルターを使用して、表示するアイテムを表示します。
- [エクスポート **] を** 選択して、結果を .csv ファイルにエクスポートします。 

## <a name="next-steps"></a>次の手順

- [修復アクションの表示と承認](manage-auto-investigation.md)
- [対話型ガイドを参照してください。 Microsoft Defender for Endpoint を使用して脅威を調査して修復する](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a>関連項目

- [エンドポイント向け Microsoft Defender で誤検知/負に対処する](defender-endpoint-false-positives-negatives.md)
