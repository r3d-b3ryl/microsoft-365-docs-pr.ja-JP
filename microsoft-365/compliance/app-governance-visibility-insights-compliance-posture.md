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
ms.openlocfilehash: 3d7cac319c31bac40a3aad2f6b9a4c16303f6a20
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420251"
---
# <a name="determine-your-app-compliance-posture"></a>アプリのコンプライアンスへの取り組みを決定する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

Microsoft アプリ ガバナンスを使用すると、[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/appgovernance)のアプリ ガバナンスの概要ページから、サード パーティ製アプリのコンプライアンスへの取り組みと、Microsoft 365 テナント内のデータへのアクセスを迅速に評価できます。

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

  - 過去 90 日間のアプリケーションの API データ アクセス
  - 過去 90 日間の上位リソースの使用状況

  この情報から、Microsoft 365 テナント内のデータへのアクセスに異常なスパイクがあるかどうかを判断できます。
