---
title: Contoso 社の Windows 10 Enterprise 展開
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が System Center Configuration Manager を使用して Windows 10 Enterprise の一括アップグレードを展開した方法について説明します。
ms.openlocfilehash: a4b24d55951c83875b9aa08db05fa4f8591472d6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869336"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Contoso 社の Windows 10 Enterprise 展開

**概要:** Contoso 社が System Center Configuration Manager を使用して Windows 10 Enterprise の一括アップグレードを展開した方法について説明します。

Microsoft 365 Enterprise の広範なロールアウトに先立ち、Contoso 社には、Windows 7 (10%)、Windows 8.1 (65%)、Windows 10 (25%) が混在する Windows 互換の PC とデバイスがありました。Contoso 社は、Windows 10 Enterprise 用の PC をアップグレードして、強化したセキュリティを利用したいと考え、更新プログラムの自動展開により IT 部門の負荷を削減しました。 

インフラストラクチャとビジネス ニーズを評価した後、Contoso 社は展開に向けて、以下の重要な要件を特定しました。

- できるだけ多くの PC やデバイスで Windows 10 Enterprise を実行する必要がある
- 一括アップグレードのロールアウトには、既存の System Center Configuration Manager インフラストラクチャを活用する
- Windows 10 Enterprise のどのバージョンを展開するかを制御し、更新プログラムはリングを介して行う
- PC やデバイスは、IT 管理コストとエンドユーザーに与える影響を最小限に抑えつつ、最新の状態に保つ必要がある

最新とは、Contoso 社のビジネス ニーズを満たす Windows 10 Enterprise のサポート バージョンとして定義されます。これは、すべての Windows 互換の PC が Windows 10 Enterprise の最新バージョンを実行することとは異なる場合があります。

## <a name="deployment-tools"></a>展開ツール

Contoso 社は、Windows 10 Enterprise の一括アップグレードの前および最中に、Windows Analytics の次のソリューションを使用しました。

- Upgrade Readiness  

  分析のためにシステム、アプリケーション、ドライバーのデータを収集し、更新の妨げになる可能性がある互換性の問題、推奨される修正、Microsoft によって既に認識されている問題を特定します。

- Update Compliance  

  更新プログラムのインストールの進行状況、Windows Update for Business (WUfB) 構成データ、Windows Defender ウイルス対策のデータ、その他の更新プログラム固有の情報を含むシステム データおよび診断データを収集し、クラウドの分析と使用のためにそのデータを保管します。

- デバイスの正常性  

  更新プログラムのインストールの進行状況、Windows Update for Business (WUfB) 構成データ、Windows Defender ウイルス対策データ、その他の更新プログラム固有の情報を含む Windows 10 のシステム データおよび診断データを収集し、クラウドを分析しおよび使用するためにこのデータを保管します。
 
Contoso 社には、既存の System Center Configuration Manager (Current Branch) インフラストラクチャがあります。Configuration Manager は大規模環境向けに拡張され、インストール、更新、設定に対する幅広い管理が可能です。また、Windows 10 Enterprise の展開と管理をより簡単で効率的にするための機能も組み込まれています。

## <a name="planning-process"></a>計画プロセス

展開に先立って、Contoso 社は次のリングを定義しました。

- 検証と展開ステージング用の 3 つのリング 
  - プレビュー ビルド用のリング 
  - 新規リリース ビルド用のリング
  - 以前のビルド用のリング 
- 検証リングからのデータに基づく Windows 10 Enterprise の幅広い展開のためのリング

Contoso 社は、Windows Analytics の Upgrade Readiness ソリューションを使用して、インストールされているアプリのセットとそれらの Windows 10 Enterprise との互換性を判断しました。

## <a name="deployment-process"></a>展開プロセス

Contoso 社は、Windows 10 Enterprise の一括アップグレードの展開を完了するために、Microsoft のベスト プラクティスの推奨事項を含む次のプロセスを実装しました。

1. 構成マネージャーのピア キャッシュを有効にしました。
2. ボリューム ライセンス サービス センターからのイメージに基づくカスタムの Windows パッケージを作成しました。
3. 構成マネージャーを使用して、ネットワーク上の配布ポイントに Windows パッケージを展開し、3 つの検証および展開ステージングのリングにビルドを展開しました。
4. Windows Analytics のデバイスの正常性および Update Compliance ソリューションを使用して、3 つの検証および展開ステージング リングで PC およびデバイスに対して成功の評価を実施しました。
5. Contoso 社は、Windows Analytics の情報に基づいて、広範な展開リングに展開する Windows 10 Enterprise のバージョンを決定しました。
6. 構成マネージャーの展開タスク シーケンスを実行して、選択した Windows パッケージを広範な展開リングに展開しました。
7. 問題に対応するために、Windows Analytics が提供するデバイスの正常性および Update Compliance ソリューションを使用して、広範な展開リング内の PC とデバイスを監視しました。

図 1 は、一括アップグレード、および進行中の更新プログラムの展開アーキテクチャを示しています。

![](./media/contoso-win10/contoso-win10-fig1.png)
 
**図 1: Contoso 社の Windows 10 Enterprise の展開インフラストラクチャ**

このインフラストラクチャは以下で構成されます。

- System Center Configuration Manager
  - Microsoft Network の Microsoft ボリューム ライセンス センターから Windows 10 Enterprise パッケージのイメージを取得します。
  - 展開パッケージに対する中央の管理ポイントです。
- 地域配布ポイント。通常は Contoso 社のサテライト オフィスにあります。
- リング メンバーシップに基づいた一括アップグレードまたは進行中の更新プログラムの展開パッケージを受信してインストールする、さまざまな場所にある Windows PC およびデバイス。

## <a name="next-step"></a>次の手順

Contoso 社が System Center Configuration Manager インフラストラクチャを利用して、現在の Office 365 ProPlus を組織全体に展開し、維持する方法について[説明](contoso-o365pp.md)します。 

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise 向け Windows 10 Enterprise](windows10-infrastructure.md)

[展開ガイド](deploy-microsoft-365-enterprise.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
