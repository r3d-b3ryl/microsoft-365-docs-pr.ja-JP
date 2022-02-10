---
title: Microsoft コンサルティング サービスを使用する
description: MCS を使用してアプリをパッケージ化するための準備と手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 5dd6bf62625d6b22a0585645abbeb24dabd6c9fd
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520453"
---
# <a name="working-with-microsoft-consulting-services"></a>Microsoft コンサルティング サービスを使用する

Microsoft コンサルティング サービス (MCS) に参加して、Microsoft マネージ デスクトップで使用するためにアプリをパッケージ化できます。 詳細については、アカウント担当者と一緒に MCS に問い合わせ、特定のアプリ パッケージ プロジェクトを確認してください。

## <a name="roles-and-responsibilities"></a>役割と責任

| 役割 | 責任 |
| ------ | ------ |
| あなたが | MCS アプリパッケージを使用するには、 **次の要素を指定する必要があります**。 <ul><li> ソース インストーラー ファイル (たとえば、setup.exeまたは.msi)。</li><li>最終的なインストールの外観に関する詳細を指定するインストール手順。 たとえば、アプリへのデスクトップ ショートカットがある必要がありますか? アプリの表示設定は何ですか? アプリがサーバーに接続する必要があります。その場合、どちらに接続しますか? 詳細については、「アプリケーション パッケージ要求 [テンプレート」を参照してください](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)。</li><li>独自の受け入れテストを実行して、アプリが環境で期待通り動作する必要があります。</li><ul> |
| Microsoft コンサルティング サービス (MCS) | **MCS は、次のアクションを処理します。** <ul><li>Microsoft Managed Desktop 環境でアプリが禁止または制限されているかどうかを確認します。</li><li>アプリのインストール、開始、アンインストールをテストして、アプリとの互換性をWindows 10。 MCS で互換性の問題が検出された場合、アプリは修復のために [App Assure プログラムに](/fasttrack/products-and-capabilities#app-assure) 渡されます。</li><li>アプリを仕様にパッケージ化し、アプリの展開をテストするには、Microsoft Intune。</li><ul>

## <a name="app-delivery-schedule"></a>アプリの配信スケジュール

アプリ情報を Microsoft Managed Desktop ポータルにアップロードして、パッケージ化プロセスを開始します。 パッケージ チームは、毎週木曜日に新しい申請を確認します。 確認とパッケージ化の後、パッケージ化されたアプリは次の金曜日に配信されます。 週に最大 5 つのアプリをパッケージ化して開始できますが、サービスはニーズに合わせて拡張できます。

![木曜日 (この例では 21 日) のアプリの流入、次の日のメディア検証、次の月曜日 (25 日) のパッケージ化、および後続の金曜日 (29 日) のアプリ配信を示すカレンダー。](../../media/MCS-cal.png)

アプリが配信された後に通知されます。 その時点で、受け入れテストを実行し、Microsoft Managed Desktop ポータルで作業を承認する 21 日間があります。 受け入れテスト中にアプリに問題が見つかった場合は、Microsoft Managed Desktop ポータルでアプリを拒否します。 問題を理解して解決するために、Microsoft Consulting Services (MCS) パッケージーと電子メールで接続されます。

## <a name="testing-accounts-and-environment"></a>アカウントと環境のテスト

パッケージ チームがパッケージ への移行を完了Microsoft Intune、特定のアクセス許可を提供することをお勧めします。

- パッケージMicrosoft Intuneアプリを追加および割り当てるアプリの展開機能へのアクセス。
- パッケージ作成者がアプリをテストできるグループ、ユーザー アカウント、ライセンスをテストします。

MCS は、これらのアクセス許可を使用して次のアクションを実行します。

- Microsoft Managed Desktop 用に構成された仮想マシンでアプリが動作するようにします。
- アップロードユーザーに展開Microsoft Intuneアプリをインストールします。

これらのアクセス許可がない場合、MCS は前進できますが、アプリケーションを環境にアップロードすることはできません。
