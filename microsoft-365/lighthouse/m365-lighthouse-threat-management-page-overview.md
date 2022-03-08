---
title: Microsoft 365 ライトハウス脅威管理ページの概要
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 ライトハウスを使用するマネージ サービス プロバイダー (MSP) の場合は、[脅威の管理] ページについて説明します。
ms.openlocfilehash: e57163ba462e241c74a96db78fe701c024a037ff
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329884"
---
# <a name="microsoft-365-lighthouse-threat-management-page-overview"></a>Microsoft 365 ライトハウス脅威管理ページの概要 

**適用対象:**

- Windows 10

Microsoft Defender Antivirus は、テナント、ユーザー、およびデバイスを、ウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威から保護します。 Windows 10 に組み込まれており、Microsoft 365 Business Premium と Microsoft365E3&nbsp;&nbsp; に含まれる堅牢で継続的な保護です。  
  
Microsoft 365 ライトハウスの [脅威管理] ページにアクセスするには、左側のナビゲーション ウィンドウで [脅威の管理] を選択して、脅威に対する顧客テナントのセキュリティ体制を表示します。 テナント、ユーザー、およびデバイスが表示され、リスクを軽減するのに役立つ注意と推奨事項が必要になります。  
  
## <a name="overview-tab"></a>[概要] タブ  
  
[脅威の管理] ページの [概要] タブで、すべてのテナントのウイルス対策状態を監視して、注意が必要な領域を特定できます。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-overview-tab.png" alt-text="[概要] タブのスクリーンショット。":::

## <a name="threats-tab"></a>[脅威] タブ

[脅威の管理] ページの [脅威] タブで、すべてのテナントでアクティブ、軽減、解決、および許可された脅威を確認できます。 また、すべてのテナントで同時に複数の脅威を修復するには、各脅威をフィルター処理して詳細に分析し、影響を受けるデバイス、ユーザー、またはテナントを確認します。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-threats-tab.png" alt-text="[既定の基準計画] ページのスクリーンショット。":::
  
次の方法で脅威をフィルター処理できます。

- 脅威の状態
- 脅威の重大度
- 脅威の種類
- 日付範囲

次の表に、さまざまな脅威の状態とその定義を示します。<br><br>

| 脅威の状態 | 定義 |
|--|--|
| 有効 | デバイスで脅威がアクティブです。 |
| 状態なし | 脅威の状態は使用できません。 デバイスでフル スキャンを実行して、Microsoft Defender Antivirus に脅威を再検出します。 |
| アクションが失敗しました | デバイスが危険にさらされていない。 アクションは失敗しましたが、潜在的な脅威は停止され、デバイスでアクティブではありません。 デバイスでフル スキャンを実行します。 |
| 手動で必要な手順 | 脅威は停止されましたが、完全スキャンやデバイスの再起動など、手動で手順を完了する必要があります。 |
| 完全スキャンが必要 | デバイスのフル スキャンが必要です。 |
| 再起動が必要 | デバイスの再起動が必要です。 |
| 重大でないエラーで修復される | 脅威は修復され、それ以上のアクションは必要とされません。 |
| 検疫済み | 脅威は検疫済みです。 それ以上のアクションは不要です。 |
| 削除 | 脅威がデバイスから正常に削除されました。 それ以上のアクションは不要です。 |
| Cleaned | Microsoft Defender ウイルス対策は、ファイルを回復および駆除しました。 それ以上のアクションは不要です。 |
| 可 | 脅威は、管理者がデバイスに残るのを許可します。 | 

## <a name="antivirus-protection-tab"></a>[ウイルス対策の保護] タブ

[脅威の管理] ページの [ウイルス対策保護] タブには、すべてのテナントのデバイスと Microsoft Defender ウイルス対策保護の状態が表示されます。 脆弱性が発生している可能性がある 1 つ以上のデバイスの状態を評価し、アクションを実行できます。 デバイスを選択して、デバイスの概要、現在の脅威、デバイス アクションの状態などの詳細を表示することもできます。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-antivirus-tab.png" alt-text="[ウイルス対策] タブのスクリーンショット。":::

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 ライトハウスベースラインの展開](m365-lighthouse-deploy-baselines.md) (記事)\
[Microsoft 365 ライトハウスに関する FAQ](m365-lighthouse-faq.yml) (記事)
