---
title: Microsoft 365 Lighthouseの [脅威管理] ページの概要
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: algreer
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
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) については、脅威管理ページを参照してください。
ms.openlocfilehash: 3d7376b2438ca24cdcf9b6e73d8bfb2cc7daa6de
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66012562"
---
# <a name="overview-of-the-threat-management-page-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseの [脅威管理] ページの概要 

**適用対象:**

- Windows

Microsoft Defender ウイルス対策は、テナント、ユーザー、デバイスを、ウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威から保護します。 Windowsに組み込まれている堅牢で継続的な保護です。  
  
Microsoft 365 Lighthouseの脅威管理ページにアクセスするには、左側のナビゲーション ウィンドウで **[脅威の管理**] を選択して、顧客テナントの脅威に対するセキュリティ体制を表示します。 リスクを軽減するのに役立つ注意と推奨事項を必要とするテナント、ユーザー、デバイスが表示されます。  
  
## <a name="overview-tab"></a>[概要] タブ  
  
[脅威管理] ページの [概要] タブで、すべてのテナントのウイルス対策状態を監視して、注意が必要な領域を特定できます。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-overview-tab.png" alt-text="[概要] タブのスクリーンショット。":::

## <a name="threats-tab"></a>[脅威] タブ

[脅威管理] ページの [脅威] タブには、すべてのテナントでアクティブ、軽減、解決済み、および許可された脅威が表示されます。 また、各脅威をフィルター処理してドリルダウンし、影響を受けるデバイス、ユーザー、またはテナントを把握することで、すべてのテナントで同時に複数の脅威を修復することもできます。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-threats-tab.png" alt-text="[既定のベースライン] ページのスクリーンショット。":::
  
次の方法で脅威をフィルター処理できます。

- 脅威の状態
- 脅威の重大度
- 脅威の種類
- 日付範囲

次の表に、さまざまな脅威の状態とその定義を示します。<br><br>

| 脅威の状態 | 定義 |
|---|---|
| Active | 脅威はデバイスでアクティブです。 |
| 状態なし | 脅威の状態は利用できません。 デバイスでフル スキャンを実行して、脅威を再検出Microsoft Defender ウイルス対策。 |
| アクションが失敗しました | デバイスは危険にさらされていません。 アクションは失敗しましたが、潜在的な脅威は停止されており、デバイスではアクティブではありません。 デバイスでフル スキャンを実行します。 |
| 手動の手順が必要です | 脅威は停止されましたが、フル スキャンやデバイスの再起動など、手動の手順を完了する必要があります。 |
| フル スキャンが必要 | デバイスのフル スキャンが必要です。 |
| 再起動が必要 | デバイスの再起動が必要です。 |
| 重大でないエラーで修復される | 脅威は修復されており、それ以上のアクションは必要ありません。 |
| 検疫 | 脅威が検疫されました。 それ以上のアクションは必要ありません。 |
| 削除 | 脅威はデバイスから正常に削除されました。 それ以上のアクションは必要ありません。 |
| 掃除 | Microsoft Defender ウイルス対策ファイルが回復され、ファイルが削除されました。 それ以上のアクションは必要ありません。 |
| 可 | 脅威は、管理者がデバイスに残ることを許可されます。 | 

## <a name="antivirus-protection-tab"></a>[ウイルス対策の保護] タブ

[脅威の管理] ページの [ウイルス対策の保護] タブには、すべてのテナントのデバイスとそのMicrosoft Defender ウイルス対策保護状態が表示されます。 状態を評価し、脆弱な可能性がある 1 つ以上のデバイスに対してアクションを実行できます。 デバイスを選択して、デバイスの概要、現在の脅威、デバイス アクションの状態などの詳細情報を表示することもできます。

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-antivirus-tab.png" alt-text="[ウイルス対策] タブのスクリーンショット。":::

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 Lighthouseベースラインをデプロイする](m365-lighthouse-deploy-baselines.md) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
