---
title: 'ステップ 5: Office 365 データ損失防止を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 の Office 365 データ損失防止を理解して展開する。
ms.openlocfilehash: 43ebfb39202e407fe6dc7bb4c8e0fe8f906f7a6d
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370164"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a>ステップ 5: Office 365 データ損失防止を構成する

*この手順は省略可能で、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*

![フェーズ 6: 情報保護](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Office 365 セキュリティ/コンプライアンス センターのデータ損失防止 (DLP) ポリシーを使用することにより、Microsoft 365 全体で機密情報の識別、監視、自動保護を行えます。 DLP ポリシーを使用すると、以下を行えます:

- Exchange Online、SharePoint Online、OneDrive for Business、Microsoft Teams などの複数の保管場所での機密情報の識別。 
- ドキュメントへのアクセスのブロックや機密情報を含むメールのブロックによる、意図しない機密情報の共有の防止。
- デスクトップ バージョンの Excel、PowerPoint、Word 内の機密情報の監視と保護。
- ワークフローを中断することなく遵守を維持する方法をユーザーが理解できるようにするための、メール通知とポリシー ヒントによるサポート。 
- 組織の DLP ポリシーと一致するコンテンツを示す DLP レポートの表示。

DLP ポリシーは、以下を指定します:

- **場所:** Exchange Online、SharePoint Online、OneDrive for Business のサイトの他、Microsoft Teams のチャットおよびチャネルなどの保管場所。
- **日時:** コンテンツが一致する必要のある特定のポリシー ルール内の条件。　
- **方法:** 一致する条件に対して自動的に実行される、一致するポリシー ルールが指定するアクション。

つまり、次のとおりです。

- 条件に一致する保管場所にあるドキュメントに対して (場所)、そのコンテンツがルールの条件に一致する場合 (日時)、そのルールが指定するアクションが自動的に実行されます (方法)。

必要な DLP ポリシー セットの決定に際しては、データ損失からの保護を必要とするドキュメントおよびそれらに含まれるデータの種類を分析する必要があります。 たとえば、米国の金融機関の場合が、社会保障番号を含むドキュメントが組織外部と共有されたり組織外部の場所にメールで送信されたりすることを防止する DLP を作成するとします。

次に、DLP の正常な動作を確認して誤検知を最小化するために、テスト用の保管場所を使用してポリシーの構成とテストを行います。

最後に、新しいポリシーおよびそれらが指定する動作を従業員に告知し、保管場所の適用範囲を広げます。このようにしてポリシーを組織で展開します。

詳細については、「[DLP ポリシーの推奨事項について](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations)」を参照してください。

中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step5)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![手順 6](./media/stepnumbers/Step6.png)|[電子メールの暗号化を構成する](infoprotect-email-encryption.md)|


