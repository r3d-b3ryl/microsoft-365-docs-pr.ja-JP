---
title: High と DoD のネットワーク セキュリティOffice 365 GCC追加の要件
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: '概要: Office 365 GCC DoD には追加のネットワーク セキュリティ要件があります'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691911"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Office 365 GCC High および DOD の追加のネットワーク セキュリティ要件

*この記事は、OFFICE 365 GCC DOD、Office 365、Microsoft 365 GCC、および DOD にMicrosoft 365します。*

Office 365 GCC高および DOD は、米国政府とそのサプライヤーおよび請負業者のニーズを満たす安全なクラウド環境です。  これらのクラウド環境には、サービスがアクセスを許可する外部エンドポイントに関する追加のネットワーク制限があります。

GCCフェデレーション ID またはハイブリッドの共同利用を計画している高値および DOD のお客様は、Microsoft が既存のオンプレミス展開への受信および/または送信アクセスを許可する必要があります。  これらのアクティビティの例を次に示します。

* フェデレーション ID の使用 (Active Directory フェデレーション サービスまたは同様のサポートされている STS を使用)
* オンプレミスの展開とハイブリッド共存Exchange ServerまたはSkype for Business展開
* オンプレミス システムからの既存のユーザー コンテンツの移行

サービスがオンプレミスのエンドポイントと通信するには、ネットワークの変更を行うエンジニアリングにOffice 365送信する必要があります。

> [!WARNING]
> すべての要求は **3** 週間の SLA を持ち、必要なセキュリティとコンプライアンスの制御と展開パイプラインのために迅速に処理することはできません。  これには、サービスに移行した後の初期オンボーディング ネットワーク要求と変更が含まれます。  ネットワーク チームがこのタイムラインを認識し、計画サイクルに含める必要があります。

ネットワーク ホワイトリストに次[Office 365 Governmentメール](mailto:o365gwlt@microsoft.com)を送信してください。

* **To**: Office 365 Government [ホワイトリスト](mailto:o365gwlt@microsoft.com)
* **From**: テナント管理者 - 送信メールが **テナント** のグローバル管理者連絡先と一致している必要があります
* **電子メール** の件名 : Office 365 GCC高ネットワーク要求 - contoso.onmicrosoft.us (テナント名に置き換えてください)

メッセージの本文には、次のデータが含まれる必要があります。

* テナントMicrosoft Online Services名 (つまり、contoso.onmicrosoft.com、fabrikam.onmicrosoft.us)
* ネットワークの変更や無効なサブネットのフォローアップに関連する、Microsoft が通信中の通信用に通信する電子メール配布リスト
* オンプレミスの展開とハイブリッドMicrosoft Teamsを使用するかどうかを示す
* フェデレーション ID システムの外部アクセス可能な URL (sts.contoso.com など) と CIDR 表記の IP アドレス範囲 (例: 10.1.1.0/28)
* CIDR 表記のオンプレミス PKI 証明書失効リスト URL と IP アドレス範囲
* CIDR 表記でのオンプレミス展開Exchange Server外部アクセス可能な URL と IP アドレスの範囲
* CIDR 表記のオンプレミス展開Skype for Business外部アクセス可能な URL と IP アドレスの範囲

セキュリティとコンプライアンスの理由から、要求に対する次の制限に注意してください。

* テナントごとに 4 つのサブネット制限があります
* サブネットは CIDR 表記 (10.1.1.0/28 など) である必要があります。
* サブネット範囲は、サブネット範囲より大/24
* 商用 **クラウド** サービス (商用クラウド サービス、Google G-Suite、Amazon Web Services など) へのアクセスを許可する要求Office 365対応できません。

要求が Microsoft によって受信および承認されると、3 週間の SLA が実装され、迅速化できません。  要求を受け取った場合は最初の確認応答を受け取り、完了したら最終的な確認を受け取る必要があります。
