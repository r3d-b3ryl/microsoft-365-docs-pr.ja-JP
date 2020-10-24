---
title: Contoso 社の Windows 10 Enterprise 展開
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が Microsoft Endpoint Configuration Manager を使用して Windows 10 Enterprise の一括アップグレードを展開した方法について説明します。
ms.openlocfilehash: 0543f24665048d0679bc1b099fdd0a2d431c1e54
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754253"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Contoso 社の Windows 10 Enterprise 展開

Microsoft 365 for enterprise の大規模な展開の前に、Contoso には windows 7 (10%)、Windows 8.1 (65%)、および Windows 10 (25%) の組み合わせを実行している Windows 互換 Pc とデバイスがありました。Windows 10 Enterprise 用に Pc をアップグレードすることを望んでいる Contoso 社は、高度なセキュリティを利用し、更新プログラムの自動展開に伴う IT オーバーヘッドを削減しました。 

インフラストラクチャとビジネス ニーズを評価した後、Contoso 社は展開に向けて、以下の重要な要件を特定しました。

- できるだけ多くの PC やデバイスで Windows 10 Enterprise を実行する必要がある
- 一括アップグレードのロールアウトには、既存の Configuration Manager インフラストラクチャを活用する
- Windows 10 Enterprise のどのバージョンを展開するかを制御し、更新プログラムはリングを介して行う
- PC やデバイスは、IT 管理コストとエンドユーザーに与える影響を最小限に抑えつつ、最新の状態に保つ必要がある

最新とは、Contoso 社のビジネス ニーズを満たす Windows 10 Enterprise のサポート バージョンとして定義されます。これは、すべての Windows 互換の PC が Windows 10 Enterprise の最新バージョンを実行することとは異なる場合があります。

## <a name="deployment-tools"></a>展開ツール

Contoso 社は、Windows 10 Enterprise の一括アップグレードの前および最中に、Windows Analytics の次のソリューションを使用しました。

- Upgrade Readiness  

  分析のためにシステム、アプリケーション、ドライバーのデータを収集し、更新の妨げになる可能性がある互換性の問題、推奨される修正、Microsoft によって既に認識されている問題を特定します。

- Update Compliance  

  Windows 更新に関するデバイスの状態が表示されるため、必要に応じて最新の更新プログラムが適用されていることを確認できます。

- デバイスの正常性  

  頻繁にクラッシュするデバイスを特定します。そのため、再構築または交換が必要になる可能性があり、デバイス クラッシュの原因となるデバイス ドライバーと、クラッシュの数を減らす可能性のあるドライバーの代替バージョンを提案します。 エンド ユーザーにプロンプ​​トを送信する Windows 情報保護の構成の誤りを通知します。
 
Contoso 社には、既存の Configuration Manager (Current Branch) インフラストラクチャがあります。Configuration Manager は大規模環境向けに拡張され、インストール、更新、設定に対する幅広い管理が可能です。また、Windows 10 Enterprise の展開と管理をより簡単で効率的にするための機能も組み込まれています。

## <a name="planning-process"></a>計画プロセス

Contoso 社は、Windows Analytics のアップグレードの準備状況を使用して、インストールされているアプリのセットと Windows 10 Enterprise との互換性を確認していました。

## <a name="deployment-process"></a>展開プロセス

Contoso 社は、Windows 10 Enterprise の一括アップグレードの展開を完了するために、Microsoft のベスト プラクティスの推奨事項を含む次のプロセスを実装しました。

1. 構成マネージャーのピア キャッシュを有効にしました。
2. ボリューム ライセンス サービス センターからのイメージに基づくカスタムの Windows パッケージを作成しました。
3. 構成マネージャーを使用して、ネットワーク経由で配布ポイントに Windows パッケージを展開し、3つの検証および展開ステージンググループにビルドを展開しました。
4. Windows Analytics のデバイスの正常性および Update Compliance ソリューションを使用して、3 つの検証および展開ステージング リングで PC およびデバイスに対して成功の評価を実施しました。
5. Windows Analytics の情報に基づき、Contoso 社は広範な展開グループに展開する Windows 10 Enterprise のバージョンを決定しました。
6. Configuration Manager 展開タスクシーケンスを実行して、選択した Windows パッケージを広範な展開グループに展開しました。
7. デバイスの状態を使用し、問題に対処するためのコンプライアンスソリューションを更新することによって、広範な展開グループ内の Pc およびデバイスを監視していました。

次に一括アップグレード、および進行中の更新プログラムの展開アーキテクチャを示します。

![Contoso 社の Windows 10 Enterprise の展開インフラストラクチャ](../media/contoso-win10/contoso-win10-fig1.png)

このインフラストラクチャは以下で構成されます。

- Configuration Manager は、以下を行います:
  - Microsoft Network の Microsoft ボリューム ライセンス センターから Windows 10 Enterprise パッケージのイメージを取得します。
  - 展開パッケージに対する中央の管理ポイントです。
- 通常は Contoso 社の地域ハブ オフィスにある地域配布ポイント。
- グループメンバーシップに基づいて一括アップグレードまたは継続的な更新の展開パッケージを受信してインストールする、さまざまな場所にある Windows Pc およびデバイス。

## <a name="next-step"></a>次のステップ

Contoso 社が構成マネージャーインフラストラクチャを活用して、組織全体で [エンタープライズ向けに現在の Microsoft 365 アプリを展開し、維持](contoso-o365pp.md) する方法について説明します。 

## <a name="see-also"></a>関連項目

[Windows 10 Enterprise](https://docs.microsoft.com/windows/deployment/)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
