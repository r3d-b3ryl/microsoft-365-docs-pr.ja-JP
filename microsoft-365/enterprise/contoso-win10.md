---
title: Contoso 社の Windows 10 Enterprise 展開
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
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
ms.openlocfilehash: 1550940afb105c569800767b2e383c6e3322c5b6
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58354814"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Contoso 社の Windows 10 Enterprise 展開

エンタープライズ向け Microsoft 365 の広範な展開に先だって、contoso 社では Windows 互換の PC とデバイスが Windows 7 (10%)、Windows 8.1 (65%)、Windows 10 (25%)の混合を実行していた。 Contoso 社は、高度なセキュリティを利用Windows 10 Enterprise、更新プログラムの自動展開による IT オーバーヘッドを削減するために、PC をアップグレードしたいと考えました。 

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

Contoso 社は、Windows Analytics のアップグレード準備を使用して、インストールされているアプリのセットと、インストールされているアプリとの互換性をWindows 10 Enterprise。

## <a name="deployment-process"></a>展開プロセス

Contoso 社は、Windows 10 Enterprise の一括アップグレードの展開を完了するために、Microsoft のベスト プラクティスの推奨事項を含む次のプロセスを実装しました。

1. 構成マネージャーのピア キャッシュを有効にしました。
2. ボリューム ライセンス サービス センターからのイメージに基づくカスタムの Windows パッケージを作成しました。
3. Configuration Manager を使用して、Windowsパッケージをネットワーク全体の配布ポイントに展開し、3 つの検証および展開ステージング グループにビルドを展開しました。
4. Windows Analytics のデバイスの正常性および Update Compliance ソリューションを使用して、3 つの検証および展開ステージング リングで PC およびデバイスに対して成功の評価を実施しました。
5. Contoso 社は、Windows分析情報に基づいて、広範な展開グループに展開するWindows 10 Enterpriseのバージョンを決定しました。
6. Configuration Manager 展開タスク シーケンスを実行して、選択した Windowsを広範な展開グループに展開しました。
7. デバイス正常性ソリューションと更新コンプライアンス ソリューションを使用して、問題に対処するために広範な展開グループ内の監視対象の PC とデバイス。

次に一括アップグレード、および進行中の更新プログラムの展開アーキテクチャを示します。

![Contoso 社の Windows 10 Enterprise の展開インフラストラクチャ](../media/contoso-win10/contoso-win10-fig1.png)

このインフラストラクチャは以下で構成されます。

- Configuration Manager は、以下を行います:
  - Microsoft Network の Microsoft ボリューム ライセンス センターから Windows 10 Enterprise パッケージのイメージを取得します。
  - 展開パッケージに対する中央の管理ポイントです。
- 通常は Contoso 社の地域ハブ オフィスにある地域配布ポイント。
- Windowsグループ メンバーシップに基づくインプレイス アップグレードまたは継続的な更新プログラムの展開パッケージを受信およびインストールするさまざまな場所の PC とデバイス。

## <a name="next-step"></a>次の手順

Contoso 社が Configuration Manager インフラストラクチャを活用して、組織全体に最新のMicrosoft 365 Apps for enterpriseを展開し、維持[する](contoso-o365pp.md)方法について説明します。 

## <a name="see-also"></a>関連項目

[Windows 10 Enterprise](/windows/deployment/)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)