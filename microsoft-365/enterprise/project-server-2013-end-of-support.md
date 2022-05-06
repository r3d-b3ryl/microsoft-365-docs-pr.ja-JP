---
title: Project Server 2013 のサポート終了ロードマップ
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
description: Project Server 2013 のサポートは、2023 年 4 月 11 日に終了します。 この記事は、オンプレミスの Project Online または新しいバージョンの Project Server にアップグレードするためのガイドとして使用します。
ms.openlocfilehash: 5a9ae38e819dfdb8f9cc2ca3719dccea2d33fa3e
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889888"
---
# <a name="project-server-2013-end-of-support-roadmap"></a>Project Server 2013 のサポート終了ロードマップ

Project Server 2013 は、**2023 年 4 月 11** 日にサポートを終了します。 Project Server 2013 を現在使用している場合は、Project 2013 デスクトップ アプリのサポート終了日も同じであることに注意してください。

## <a name="what-does-end-of-support-mean"></a>*サポート終了とは* どういう意味ですか?

ほぼすべての Microsoft 製品にはサポート ライフサイクルがあり、その間に新機能、バグ修正、およびセキュリティ更新プログラムが提供されます。 このライフサイクルは通常、製品の初期リリースから 10 年間続きます。 このライフサイクルの終了は、製品のサポート終了と呼ばれます。 Project Server 2013 が 2023 年 4 月 11 日にサポートの終了に達すると、Microsoft は次の情報を提供しなくなります。

- 発生する可能性がある問題のテクニカル サポート。

- 検出され、サーバーの安定性と使いやすさに影響を与える可能性がある問題に対するバグ修正。

- 検出され、サーバーがセキュリティ違反に対して脆弱になる可能性がある脆弱性に対するセキュリティ修正。

- タイム ゾーンの更新。

Project Server 2013 のインストールは、この日以降も引き続き実行されます。 ただし、前述の変更のため、できるだけ早く Project Server 2013 から移行することを強くお勧めします。

## <a name="what-are-my-options"></a>使用できるオプション

移行オプションは次のとおりです。

- Project Onlineに移行する

- 新しいオンプレミス バージョンの Project Server に移行する (できればProject Server サブスクリプション エディション)

|Project Server 2019 に移行する必要があるのはなぜですか?|Project Onlineに移行する必要があるのはなぜですか?|
|---|---|
|ビジネス ルールを使用すると、クラウドでのビジネスの運用が制限されます。  <br/><br/>  環境の更新を制御する必要があります。|モバイル ユーザーまたはリモート ユーザーがいます。<br/><br/>  オンプレミス サーバーを移行するためのコストは、大きな懸念事項 (ハードウェア、ソフトウェア、実装にかかる時間と労力など) です。 <br/><br/>  移行後、環境を維持するためのコストが懸念されます (自動更新、稼働時間の保証など)。|

> [!NOTE]
> Project サーバーは、Project サーバーとProject Onlineが同じリソース プールを共有できないため、ハイブリッド構成をサポートしていません。

## <a name="important-considerations-for-migrating-from-project-server-2013"></a>Project Server 2013 からの移行に関する重要な考慮事項

Project Server 2013 から移行する場合は、次の点を考慮してください。

- **Microsoft ソリューション プロバイダーからヘルプを受ける** - Project Server 2013 からのアップグレードは困難な場合があります。 多くの準備と計画が必要です。 最初にサーバー 2013 をセットアップしたユーザーでない場合は、特に困難Project可能性があります。 microsoft ソリューション プロバイダーは、Project Server サブスクリプション エディションに移行する場合でも、Project Onlineに移行する場合でも、役立ちます。 Microsoft ソリューション プロバイダー [センターでソリューション プロバイダー](https://go.microsoft.com/fwlink/p/?linkid=841249)を検索します。

- **時間と忍耐** - アップグレードの計画、実行、テストには、特にProject Server サブスクリプション エディションへのアップグレードにかなりの時間と労力がかかります。 Project Server 2013 から Project Server サブスクリプション エディションに移行する場合は、まずProject Server 2016に移行し、データを確認してから、Project Server サブスクリプション エディションする必要があります。 Microsoft ソリューション プロバイダーに対して、期間とコストの見積もりを確認することをお勧めします。

## <a name="migrate-to-project-online"></a>Project Onlineに移行する

Project Server 2013 から Project Onlineに移行することを選択した場合は、次の手順に従ってプロジェクト 計画データを手動で移行できます。

1. プロジェクト プランを Project Server 2013 から .mpp 形式に保存します。

2. Project Professional 2016、Project Professional 2019、またはProject Online デスクトップ クライアントを使用して、各 .mpp ファイルを開き、Project Onlineに保存して発行します。

Project OnlineでPWA構成を手動で作成できます (たとえば、必要なユーザー設定フィールドやエンタープライズ カレンダーを再作成します)。 Microsoft ソリューション プロバイダーは、このプロセスにも役立ちます。

主なリソース:

|関連情報|説明|
|---|---|
|[Project Online の使用を開始する](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Project Onlineを設定して使用する方法|
|[Project Online サービスの説明](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|利用可能なさまざまなProject Onlineプランに関する情報|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>新しいオンプレミス バージョンの Project Server に移行する

Project Onlineに移行することで、お客様が最高の価値とユーザー エクスペリエンスを得られると強く信じています。 ただし、一部の組織では、プロジェクト データをオンプレミスに保持する必要があることも理解しています。 プロジェクト データをオンプレミスに保持する場合は、Project Server 2013 環境をProject Server 2016、Project Server 2019、またはProject Server サブスクリプション エディションに移行できます。

Project Onlineに移行できない場合は、Project Server の以前のリリースの主な機能のほとんどを含むProject Server サブスクリプション エディションに移行することをお勧めします。 また、Project Onlineで使用できるエクスペリエンスと最もよく一致しますが、一部の機能はProject Onlineでのみ使用できます。 考慮すべきその他の要因は次のとおりです。

- Project Server サブスクリプション エディションでは、Project Server の新しいメジャー バージョンを今後リリースする必要のない継続的な更新モデルが導入されています。
- Project Server 2016と 2019 の両方が、2026 年 7 月 14 日にサポートを終了します。 どちらのバージョンにも移行する場合は、3 年間で別のアップグレードを計画する必要があります。 詳細については、 [2016 と 2019](/lifecycle/products/project-server-2016) の両方のサポート ライフサイクル ページ [を参照](/lifecycle/products/project-server-2019)してください。

各移行が完了したら、データが正常に移行されたことを確認します。

### <a name="how-do-i-migrate-to-project-server-subscription-edition"></a>Project Server サブスクリプション エディションに移行操作方法?

Project Server 2013 と Project Server サブスクリプション エディションのアーキテクチャ上の違いにより、直接移行パスが回避されます。 そのため、Project Server 2013 データを最初にProject Server 2016に移行してから、Project Server サブスクリプション エディションに移行する必要があります。 

1. Project Server 2016に移行します。

2. Project Server 2016からProject Server サブスクリプション エディションに移行します。

各移行が完了したら、データが正常に移行されたことを確認します。

### <a name="step-1-migrate-to-project-server-2016"></a>手順 1: Project Server 2016に移行する

Project Server 2013 から Project Server 2016へのアップグレードに関する包括的な情報については、「[Project Server 2016へのアップグレード」を](/project/upgrade-to-project-server-2016)参照してください。

主なリソース:

- [Project Server 2016アップグレード プロセスの概要](/project/upgrade-to-project-server-2016): Project Server 2013 から Project Server 2016にアップグレードする方法の概要を確認します。
- [Project Server 2016にアップグレードする計画](/project/plan-for-upgrade-to-project-server-2016): システム要件を含め、Project Server 2013 から Project Server 2016にアップグレードする際の計画に関する考慮事項を確認します。
- [Project Server 2016へのアップグレード](/project/upgrading-to-project-server-2016): アップグレード プロセスの詳細な手順を参照してください。

### <a name="step-2-migrate-to-project-server-subscription-edition"></a>手順 2: Project Server サブスクリプション エディションに移行する

Project Server 2016に移動し、データが正常に移行されたことを確認したら、次の手順ではProject Server サブスクリプション エディションに移行します。

詳細については、「[Project Server サブスクリプション エディションへのアップグレード」を](/project/upgrade-project-server-subscription-edition)参照してください。

主なリソース:

- [Project Server サブスクリプション エディションアップグレード プロセスの概要](/project/overview-project-server-subscription-edition-upgrade-process): Project Server 2013 から Project Server 2016 にアップグレードするために必要な作業について説明します。
- [Project Server サブスクリプション エディションへのアップグレードを計画する](/Project/plan-upgrade-project-server-subscription-edition): Project Server 2013 から Project Server 2016 にアップグレードする際の計画に関する考慮事項を確認します。
- [Project Server サブスクリプション エディションへのアップグレード](/project/how-to-upgrade-project-server-subscription-edition): アップグレード プロセスの詳細な手順を参照してください。


