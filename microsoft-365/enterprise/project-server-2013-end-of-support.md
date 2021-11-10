---
title: ProjectServer 2013 のサポート終了ロードマップ
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 10/11/2021
audience: ITPro
ms.topic: conceptual
ms.prod: project-server-itpro
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
description: 2023 年 4 月 11 日Project Server 2013 のサポートは終了します。 この記事をガイドとして使用して、Project Onlineまたは新しいバージョンの Projectサーバーにアップグレードします。
ms.openlocfilehash: 5a9ae38e819dfdb8f9cc2ca3719dccea2d33fa3e
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889888"
---
# <a name="project-server-2013-end-of-support-roadmap"></a>ProjectServer 2013 のサポート終了ロードマップ

Projectサーバー 2013 は **、2023** 年 4 月 11 日にサポートの終了に達します。 現在、Project Server 2013 を使用している場合は、Project 2013 デスクトップ アプリのサポート終了日も同じに注意してください。

## <a name="what-does-end-of-support-mean"></a>サポート終了 *とはどういう意味* ですか?

ほとんどすべての Microsoft 製品にはサポート ライフサイクルが含まれています。その間、新機能、バグ修正、セキュリティ更新プログラムが提供されます。 このライフサイクルは、通常、製品の最初のリリースから 10 年間続く。 このライフサイクルの終了は、製品のサポート終了と呼ばれる。 2013 Project 2013 が 2023 年 4 月 11 日にサポートの終了に達すると、Microsoft は次の情報を提供しなくなりました。

- 発生する可能性のある問題に対するテクニカル サポート。

- 検出され、サーバーの安定性と使いやすさに影響を与える可能性がある問題のバグ修正。

- 検出され、サーバーがセキュリティ侵害に対して脆弱になる可能性がある脆弱性に対するセキュリティ修正。

- タイム ゾーンの更新。

サーバー 2013 Projectのインストールは、この日付以降も実行されます。 ただし、前に示した変更のため、できるだけ早く Project Server 2013 から移行することを強く推奨します。

## <a name="what-are-my-options"></a>使用できるオプション

移行オプションは次のとおりです。

- 移行してProject Online

- 新しいオンプレミス バージョンの Project サーバーに移行する (Project サーバー サブスクリプション エディション)

|サーバー 2019 への移行Projectする理由|移行先に移行する理由Project Online。|
|---|---|
|ビジネス ルールは、クラウドでのビジネスの運用を制限します。  <br/><br/>  環境の更新を制御する必要があります。|モバイル ユーザーまたはリモート ユーザーがいます。<br/><br/>  オンプレミス サーバーを移行するためのコストは重要な懸念事項です (ハードウェア、ソフトウェア、実装の時間と労力など)。 <br/><br/>  移行後、環境を維持するためのコストが懸念されます (自動更新、保証されたアップタイムなど)。|

> [!NOTE]
> Projectサーバーとサーバーは同じリソース プールProject共有Project Onlineハイブリッド構成をサポートしません。

## <a name="important-considerations-for-migrating-from-project-server-2013"></a>サーバー 2013 から移行する際Project考慮事項

サーバー 2013 から移行する予定の場合は、次Project検討してください。

- **Microsoft ソリューション プロバイダーからヘルプを受ける**- サーバー 2013 Projectアップグレードは難しい場合があります。 多くの準備と計画が必要です。 サーバー 2013 で最初にセットアップしたユーザーでなかった場合は、特にProjectがあります。 Microsoft ソリューション プロバイダーは、サーバー サブスクリプション エディションへの移行を計画Project、またはサーバーサブスクリプションに移行Project Online。 Microsoft ソリューション プロバイダー センターでソリューション プロバイダー [を検索します](https://go.microsoft.com/fwlink/p/?linkid=841249)。

- **時間と忍耐**- アップグレードの計画、実行、およびテストには、特にサーバー サブスクリプション エディションへのアップグレードには、かなりの時間と労力Project必要があります。 Project Server 2013 から Project Server サブスクリプション エディションに移行する場合は、まず Project Server 2016 に移行し、データを確認してから、Project Server サブスクリプション エディションに移行する必要があります。 Microsoft ソリューション プロバイダーに時間と見積もりコストを確認して支援する必要がある場合があります。

## <a name="migrate-to-project-online"></a>移行してProject Online

Project サーバー 2013 から Project Online に移行する場合は、次の手順に従って、プロジェクト 計画データを手動で移行できます。

1. プロジェクト プランをサーバー 2013 Project .mpp 形式に保存します。

2. Project Professional 2016、Project Professional 2019、または Project Online デスクトップ クライアントを使用して、各 .mpp ファイルを開き、そのファイルを保存して Project Online に発行します。

ユーザー設定は、PWA手動Project Online作成できます (たとえば、必要なユーザー設定フィールドやエンタープライズ カレンダーを再作成します)。 Microsoft ソリューション プロバイダーは、このプロセスにも役立ちます。

主なリソース:

|関連情報|説明|
|---|---|
|[Project Online の使用を開始する](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|ユーザー設定と使用方法Project Online|
|[Project Online サービスの説明](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|利用可能なさまざまなプランProject Online情報|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>新しいオンプレミス バージョンの Project サーバーに移行する

お客様が最適な価値とユーザー エクスペリエンスを得たと強く信じています。Project Online。 ただし、一部の組織では、プロジェクト データをオンプレミスに保持する必要がある場合もあります。 プロジェクト データをオンプレミスに保持する場合は、Project Server 2013 環境を Project Server 2016、Project Server 2019、または Project Server Subscription Edition に移行できます。

Project Online に移行できない場合は、Project Server サブスクリプション エディション (Project Server の以前のリリースの主要な機能のほとんどを含む) に移行することをお勧めします。 また、一部の機能はProject Onlineでしか使用できないが、Project Online。 考慮すべきその他の要因は次のとおりです。

- ProjectServer Subscription Edition では、継続的な更新モデルが導入され、今後、新しいメジャー バージョンの Projectをリリースする必要がなくなっています。
- 2019 Project Server 2016 2019 年は、2026 年 7 月 14 日にサポートが終了します。 いずれかのバージョンに移行する場合は、3 年後に別のアップグレードを計画する必要があります。 詳細については [、2016 と 2019](/lifecycle/products/project-server-2016) の両方のサポート ライフサイクル ページ [を参照してください](/lifecycle/products/project-server-2019)。

各移行が完了したら、データが正常に移行されたことを確認します。

### <a name="how-do-i-migrate-to-project-server-subscription-edition"></a>サーバー サブスクリプション エディションに移行Project方法

サーバー 2013 Projectサーバー サブスクリプション エディションProjectアーキテクチャの違いにより、直接移行パスが妨がっています。 そのため、最初にサーバー 2013 Projectデータを移行しProject Server 2016サーバー サブスクリプション エディションProjectする必要があります。 

1. [移行] Project Server 2016。

2. サーバー サブスクリプション エディションProject Server 2016からProject移行します。

各移行が完了したら、データが正常に移行されたことを確認します。

### <a name="step-1-migrate-to-project-server-2016"></a>手順 1: 移行してProject Server 2016

サーバー 2013 からサーバー 2013 へのアップグレードProject詳細については、「upgrade [to Project Server 2016」を参照Project Server 2016。](/project/upgrade-to-project-server-2016)

主なリソース:

- [アップグレード プロセスProject Server 2016概要](/project/upgrade-to-project-server-2016): Project Server 2013 からサーバー 2013 へのアップグレード方法の概要をProject Server 2016。
- Project Server 2016 へのアップグレード[を計画する](/project/plan-for-upgrade-to-project-server-2016): Project Server 2013 から Project Server 2016 にアップグレードする際の計画上の考慮事項 (システム要件を含む) を参照してください。
- [[アップグレードProject Server 2016:](/project/upgrading-to-project-server-2016)アップグレード プロセスの詳細な手順を参照してください。

### <a name="step-2-migrate-to-project-server-subscription-edition"></a>手順 2: サーバー サブスクリプション エディションProject移行する

サーバー に移動しProject Server 2016が正常に移行されたことを確認した後、次の手順では、サーバー サブスクリプション エディションProject移行します。

詳細については[、「Upgrade to Project Server Subscription Edition」を参照してください](/project/upgrade-project-server-subscription-edition)。

主なリソース:

- [Project サーバー サブスクリプション](/project/overview-project-server-subscription-edition-upgrade-process)エディションのアップグレード プロセスの概要 : Project Server 2013 からサーバー へのアップグレードに必要なProject Server 2016。
- [Project Server サブスクリプション](/Project/plan-upgrade-project-server-subscription-edition)エディションへのアップグレードを計画する: Project Server 2013 から Project Server 2016 にアップグレードする際の計画上の考慮事項を参照してください。
- [サーバー サブスクリプション エディションProjectアップグレード](/project/how-to-upgrade-project-server-subscription-edition): アップグレード プロセスの詳細な手順を参照してください。


