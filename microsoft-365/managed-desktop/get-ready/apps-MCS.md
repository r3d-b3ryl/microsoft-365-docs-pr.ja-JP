---
title: Microsoft コンサルティング サービスを使用する
description: アプリケーションをパッケージ化するために MCS と連携するための準備と手順
keywords: Microsoft マネージドデスクトップ、Microsoft 365、service、ドキュメント、アプリ、MCS、パッケージ
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0cb4da85b5548ced757197a3af818e212b065b47
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085943"
---
# <a name="working-with-microsoft-consulting-services"></a>Microsoft コンサルティング サービスを使用する

Microsoft コンサルティングサービス (MCS) と協力して、Microsoft マネージドデスクトップで使用するためにアプリをパッケージ化することができます。 詳細については、アカウント担当者と連携して MCS と連絡をとって、特定のアプリパッケージプロジェクトの範囲を指定します。

## <a name="roles-and-responsibilities"></a>役割と責任

MCS アプリパッケージを使用するには、**次の要素を提供する必要があり**ます。

- ソースインストーラファイル (例: setup.exe または .msi)。
- インストール手順で、最終的なインストール方法の詳細を指定します。 たとえば、アプリにデスクトップショートカットがあるかどうかを確認します。 アプリの可視性をどのようにする必要がありますか? アプリをサーバーに接続し、その場合はどうすればよいですか。 詳細については、「[アプリケーションパッケージ要求テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)」を参照してください。
- アプリが環境内で必要なときに動作することを確認するために、独自の受け入れテストを実行する必要があります。

**MCS は、次の操作を行います。**

- Microsoft マネージドデスクトップ環境でアプリが禁止または制限されているかどうかを確認します。
- Windows 10 との互換性を確保するために、アプリのインストール、開始、アンインストールをテストします。 MCS が互換性の問題を検出した場合は、アプリを[デスクトップアプリ](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure)に渡して、修復のためのプログラムを確実に実行します。
- アプリを仕様にパッケージ化し、Microsoft Intune を使用してアプリの展開をテストします。

## <a name="app-delivery-schedule"></a>アプリの配信スケジュール

アプリの情報を Microsoft マネージドデスクトップポータルにアップロードして、パッケージ化プロセスを開始します。 パッケージチームは、毎週木曜日に新しい提出をレビューします。 レビューとパッケージ化後、パッケージ化されたアプリは次の金曜日に配信されます。 1週間に最大5つのアプリを開始するためのパッケージを作成できますが、サービスはニーズに合わせて拡張できます。

![木曜日にアプリケーションのインフロー (この例では 21)、次の日にメディア検証、次の月曜日にパッケージ化 (25)、以降の金曜日にアプリの配信を示すカレンダー (29 日)](../../media/MCS-cal.png)

アプリが配信されると、通知されます。 その時点で、承認テストを実行し、Microsoft マネージドデスクトップポータルで作業を行うことができるのは、21日です。 受け入れテストの間にアプリに関して何らかの問題が見つかった場合は、Microsoft マネージドデスクトップポータルでアプリを拒否すると、問題を把握して解決するために、メールで MCS パッケージャーに接続されます。

## <a name="testing-accounts-and-environment"></a>アカウントと環境のテスト

パッケージ化チームが Microsoft Intune への移行を完了するには、次のアクセス許可を付与することをお勧めします。
 
-   アプリの追加と割り当てに使用するための、Microsoft Intune のアプリ展開機能へのアクセス 
-   Packagers がアプリをテストできるようにするためのグループ、ユーザーアカウント、およびライセンスをテストします。

MCS は、これらのアクセス許可を使用して、次の操作を実行します。
 
-   Microsoft マネージドデスクトップ用に構成された仮想マシン上でアプリが動作することを確認する
-   ユーザーに展開するためにアプリを Microsoft Intune にアップロードする

これらのアクセス許可がないと、MCS は先に進むことができますが、アプリケーションを環境にアップロードすることはできません。


