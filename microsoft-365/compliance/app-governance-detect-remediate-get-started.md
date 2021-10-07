---
title: アプリの脅威の検出と修復を開始する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: アプリの脅威の検出と修復を開始する。
ms.openlocfilehash: 7bf3e716bfa84161503ad656264ada82adc2bd6b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188375"
---
# <a name="get-started-with-app-threat-detection-and-remediation"></a>アプリの脅威の検出と修復を開始する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

Microsoft アプリ ガバナンスは、悪意のあるアプリに基づいて組み込みのアプリ ガバナンス検出方法により生成された脅威アラート、および作成したアクティブなアプリ ポリシーによって生成されたポリシー ベースのアラートを収集します。

アプリのアラートを表示する最初の場所は、[https://aka.ms/appgovernance](https://aka.ms/appgovernance) のアプリ ガバナンス ダッシュボードです。

![Microsoft 365 コンプライアンス センターの [検出とポリシーアラート] セクションが強調表示されている [アプリ ガバナンスの概要] ページ。](..\media\manage-app-protection-governance\mapg-cc-overview-alerts.png)

この概要ページの [**検出とポリシーのアラート**] セクションに、最新のアラートが一覧表示されます。 これを使用すると、テナントの現在のアプリ アラート アクティビティをすばやく表示できます。

すべてのアラートを表示するには、[**アラート**] タブを選択します。

## <a name="whats-available-on-the-alerts-page"></a>[アラート] ページで使用できる機能

[**アラート**] ページには、テナントのすべてのアプリ ガバナンス ベースのアラートが一覧表示されます。

![Microsoft 365 コンプライアンス センターの [アプリ ガバナンス アラートの概要] ページ。](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

リストされたそれぞれのアラートには、次の情報が含まれています:

- **アラート名**: 異常な動作の種類。
- **アプリ名**: アラートを生成したアプリ。
- **重大度**: 作成されたアラートのアプリ ガバナンスによって割り当てられた重大度、またはアラートを生成したアプリ ポリシーの重大度。
- **ソース**: アラートの発生元。これは、ポリシー (ユーザーが作成したポリシー)、検出 (組み込みの検出ポリシー)、または MCAS からの結果である可能性があります。
- **状態**: **新規** は、状態が割り当てられていないアラートを示します。 割り当てられた状態は、調査中には **進行中** か、自動修復または手動修復によって対処されたアラートについては **解決済み** のいずれかになります。
- **作成日**: アプリ ガバナンス検出またはアプリ ポリシーを介してアラートが生成された日付。 表示されている日付はすべて、Microsoft 365 コンプライアンス センターのローカル タイム ゾーンに基づいています。
- **最後のアクティビティ**: アラートの状態が最後に変更された日付。 表示されている日付はすべて、Microsoft 365 コンプライアンス センターのローカル タイム ゾーンに基づいています。

既定では、アラート一覧は **作成日** 順に並べ替えられます。 リストを別の属性で並べ替えるには、属性名を選択します。

ポリシー一覧をコンマ区切り値 (CSV) ファイルにエクスポートすることもできます。 たとえば、Microsoft Excel で CSV ファイルを開き、**重大度** と **アラートの合計数** でポリシーを並べ替えることができます。

## <a name="next-step"></a>次の手順

[異常検出アラートを調査する](app-governance-anomaly-detection-alerts.md)
