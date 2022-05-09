---
title: Office 365 GCC High および DoD に関する追加のネットワーク セキュリティ要件
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
description: '概要: Office 365 GCC High と DoD には追加のネットワーク セキュリティ要件があります'
hideEdit: true
ms.openlocfilehash: c4fbfc52085b634329130c2785ce683109b8febe
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170369"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Office 365 GCC High および DOD の追加のネットワーク セキュリティ要件

*この記事は、Office 365 GCC High、Office 365 DOD、Microsoft 365 GCC High、Microsoft 365 DOD に適用されます。*

Office 365 GCC High と DOD は、米国政府機関とそのサプライヤーや請負業者のニーズを満たすセキュリティで保護されたクラウド環境です。  これらのクラウド環境には、サービスがアクセスを許可されている外部エンドポイントに対する追加のネットワーク制限があります。

GCC フェデレーション ID またはハイブリッド共存を使用することを計画している高および DOD のお客様は、Microsoft が既存のオンプレミス展開への受信または送信アクセスを許可する必要がある場合があります。  これらのアクティビティの例を次に示します。

* フェデレーション ID の使用 (Active Directory フェデレーション サービス (AD FS)または同様にサポートされている STS を使用)
* オンプレミスのExchange ServerまたはSkype for Businessデプロイとのハイブリッド共存
* オンプレミス システムからの既存のユーザー コンテンツの移行

サービスがオンプレミスエンドポイントと通信できるようにするには、ネットワーク変更のためにOffice 365エンジニアリングに電子メールを送信する **必要があります**。

> [!WARNING]
> すべての要求には **3 週間の** SLA があり、必要なセキュリティとコンプライアンスの制御とデプロイ パイプラインのために迅速化することはできません。  これには、初期のオンボード ネットワーク要求と、サービスに移行した後の変更が含まれます。  ネットワーク チームがこのタイムラインを認識していることを確認し、計画サイクルに含めます。

次の情報を[Office 365 Government Allow-List要求](mailto:o365gwlt@microsoft.com)に電子メールを送信します。

* **To**: [Office 365 Government Allow-List requests](mailto:o365gwlt@microsoft.com)
* **From**: テナント管理者 - 送信電子メールは、テナント内のグローバル管理者の連絡先と一致 **する必要があります**
* **電子メールの件名**: Office 365 GCC高ネットワーク要求 - contoso.onmicrosoft.us (テナント名に置き換えます)

メッセージの本文には、次のデータを含める必要があります。

* Microsoft Online Services テナント名 (contoso.onmicrosoft.com、fabrikam.onmicrosoft.us など)
* ネットワークの変更や無効なサブネットのフォローアップに関連する継続的な通信のために Microsoft が通信する電子メール配布リスト
* オンプレミスのデプロイとハイブリッド共存Microsoft Teams使用するかどうかを指定する
* フェデレーション ID システムの外部からアクセス可能な URL (sts.contoso.com など) と IP アドレス範囲 (CIDR 表記など)。 10.1.1.0/28)
* オンプレミス PKI 証明書失効リストの URL と IP アドレス範囲 (CIDR 表記)
* CIDR 表記でオンプレミス展開をExchange Serverするための外部からアクセス可能な URL と IP アドレス範囲
* CIDR 表記でオンプレミス展開をSkype for Businessするための外部からアクセス可能な URL と IP アドレス範囲

セキュリティとコンプライアンスの理由から、要求に関する次の制限に注意してください。

* テナントごとに 4 つのサブネット制限があります
* サブネットは CIDR 表記である必要があります (たとえば、10.1.1.0/28)
* サブネット範囲を/24より大きくすることはできません
* 商用クラウド サービス (商用Office 365、Google G-Suite、Amazon Web Services など) へのアクセスを許可する要求には対応 **できません**。

Microsoft によって要求が受信および承認されると、実装に対して 3 週間の SLA があり、迅速に実行することはできません。  要求を受け取ったときに最初の確認が届き、完了すると最終的な確認が届きます。
