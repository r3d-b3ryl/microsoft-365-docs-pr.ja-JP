---
title: 'ステップ 5: Office 365 データ損失防止を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 で Office 365 データ損失防止を理解して展開します。
ms.openlocfilehash: d0a8beae3797e59eb1eb130afb9fd123be57d909
ms.sourcegitcommit: 9d4319a015e493fb88c7e1855bca0121654eb39d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2019
ms.locfileid: "33308353"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a>ステップ 5: Office 365 データ損失防止を構成する

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Office 365 セキュリティ & コンプライアンス センターのデータ損失防止 (DLP) ポリシーにより、Microsoft 365 全体の機密情報の識別、監視、自動保護ができます。 DLP ポリシーを用いて次が行えます:

- Exchange Online、SharePoint Online、OneDrive for Business、Microsoft Teams などの複数の保管場所のまたがる機密情報を識別します。 
- ドキュメントへのアクセスをブロックしたり、機密情報を含むメールをブロックしたりすることで、意図しない機密情報の共有を防ぎます。
- デスクトップ バージョンの Excel、PowerPoint、Word 内の機密情報を監視し、保護します。
- メール通知とポリシー ヒントを用いて、ワークフローを中断することなく準拠した状態を保つ方法をユーザーが理解するのを助けます。 
- 組織の DLP ポリシーと一致するコンテンツを示す DLP レポートを表示します。

DLP ポリシーでは次を指定します:

- **場所:** Microsoft Teams のチャットおよびチャネルと、Exchange Online、SharePoint Online、OneDrive for Business、Microsoft Teamsなどの保管場所。
- **日時:** 特定のポリシー ルールの範囲内でコンテンツが一致する必要のある条件。　
- **方法:** ポリシー ルールに一致している範囲内での一致条件に対応する自動的なアクション。

つまり、次のとおりです。

- 上記の保管場所内 (場所) のドキュメントの場合、ルール (日時) の条件がコンテンツと一致していれば、ルールで指定されたアクション (方法) を自動的に実行します。

必要な DLP ポリシー セットを決定するには、データ損失からの保護を必要とする範囲内のドキュメントとデータの種類を解析する必要があります。 たとえば、米国の金融機関の場合は、社会保障番号と共にドキュメントが組織の外で共有されたり、組織の外の保管場所にメールで送信されたりするのを防ぐ DLP ポリシーを作成します。

次に、正しい DLP の動作を保証して誤検知を最小化するところの保管場所のテストと共にポリシーの設定とテストを行います。

最後に、従業員の新しいポリシーと従業員として望ましい行動の通知と、保管場所の適用範囲の拡張を行うことにより、組織へとそのポリシーを展開します。

詳細については、[DLP のポリシー勧告を見る](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations)を参照してください。

中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step5)を確認できます。

## <a name="next-step"></a>次の手順


|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)|[Office 365 の特権アクセス管理を構成する](infoprotect-configure-privileged-access-management.md)|


