---
title: アプリのコンプライアンスへの取り組みを決定する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: アプリのコンプライアンスへの取り組みを決定する。
ms.openlocfilehash: 08fccdb5b6d82e798a8c0eda99db988505800610
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53541195"
---
# <a name="determine-your-app-compliance-posture"></a>アプリのコンプライアンスへの取り組みを決定する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

Microsoft アプリ ガバナンスを使用すると、Microsoft 365 コンプライアンス センターのアプリ ガバナンスの概要ページから、サード パーティ製アプリのコンプライアンスへの取り組みと、Microsoft 365 テナント内のデータへのアクセスを迅速に評価できます。

![Microsoft 365 コンプライアンス センターの [アプリ ガバナンス概要] ページ](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> アプリ ガバナンス データを表示するには、サインイン アカウントに[これらのロール](app-governance-get-started.md#administrator-roles)のいずれかが必要です。
>

このページから次の情報が確認できます:

- Microsoft Graph API を使用する OAuth 対応アプリの場合:

  - テナント内のアプリの数
  - 特権が過剰である可能性のあるアプリの数
  - 高い特権のアプリの数

  この情報から、特権が過剰なアプリや高い特権を持つアプリによって、組織が晒されるリスクのレベルを判断できます。

- アラートの場合:

  - テナントに含まれているアクティブなアラートの数
  - アプリ ガバナンスの検出に基づく数 (**脅威アラート**)
  - 設定されているアプリ ポリシーに基づく数 (**ポリシー アラート**)
  - 最新の 10 件のアラート

  この情報から、アラートの生成速度と、検出されたアラートとポリシー ベースのアラートの相対的な数を確認できます。

- データとリソースへのアクセス:

  - テナント内のアプリが、現在と過去 3 か月間にGraph API経由でアクセスした合計データ。 (現在のところ、Outlook メール とファイルのアップロードとダウンロードの使用状況のみが含まれています)
  - リソース種類別の、現在と過去 3 か月間のデータ使用状況。 (現在のところ、Outlook メール とファイルのアップロードとダウンロードの使用状況のみが含まれています)

  この情報から、Microsoft 365 テナント内のデータへのアクセスに異常なスパイクがあるかどうかを判断できます。
