---
title: インプレース アップグレードによる Windows 10 Enterprise の既存デバイスへの展開
description: Microsoft エンドポイント構成マネージャーを一括アップグレードとして使用して Windows 10 Enterprise イメージを構成および展開する方法についてのガイダンスを提供します。
keywords: Microsoft 365、Microsoft 365 Enterprise、Microsoft 365 ドキュメント、Windows 10 Enterprise、deployment、一括アップグレード、構成マネージャー、構成マネージャー
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 27ed024c47ac671625563d8bf060017cb1757c4c
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112691"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a>手順 2: 既存のデバイス用に Windows 10 Enterprise を一括アップグレードとして展開する

*この記事は、Microsoft 365 Enterprise の E3 および E5 の両バージョンに適用されます*

![フェーズ 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

現在 Windows 7 または Windows 8.1 を実行している Pc をアップグレードするための最も単純なパスは、一括アップグレードを使用しています。 構成マネージャー (構成マネージャー) のタスクシーケンスを使用して、プロセスを完全に自動化することができます。 

Windows 7 または Windows 8.1 を実行している既存のコンピューターがある場合は、組織で Windows 10 を展開している場合はこのパスを使用することをお勧めします。 Windows インストールプログラム (Setup.exe) を活用して一括アップグレードを実行すると、既存のオペレーティングシステムのバージョンからすべてのデータ、設定、アプリケーション、およびドライバーが自動的に保持されます。 複雑な展開インフラストラクチャは必要ないため、これには最小限の IT 作業が必要になります。

Microsoft エンドポイント構成マネージャーを一括アップグレードとして使用して Windows 10 Enterprise イメージを構成および展開するには、次の手順を実行します。

## <a name="the-windows-10-deployment-with-configuration-manager-poster"></a>構成マネージャーポスターを使用した Windows 10 展開

構成マネージャーのポスターは、横モード (17x11) の1つのページです。 ブラウザーに PDF を表示するには、以下の画像をクリックします。 

[![構成マネージャーポスターを使用して Windows 10 を展開する](./media/windows10-deploy-inplaceupgrade/windows10-deployment-config-manager.png)](https://docs.microsoft.com/windows/deployment/media/Windows10DeploymentConfigManager.pdf)

このポスターを [PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.pdf) または [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.vsdx) 形式でダウンロードすることもできます。

## <a name="part-1-verify-readiness-to-upgrade-windows"></a>パート 1: Windows のアップグレードの準備を確認する

最初に、Windows Analytics のアップグレード準備機能を使用して、組織内のコンピューター、アプリケーション、およびドライバーに関する強力な洞察と推奨事項を、追加の費用をかけることなく、追加のインフラストラクチャ要件を伴わずに提供します。 この新しいサービスは、Microsoft が推奨する方法に基づいてワークフローを使用して、アップグレードと機能の更新プロジェクトを案内します。 最新の在庫データを使用すると、アップグレードプロジェクトのコストとリスクのバランスを取ることができます。

詳細については、「[アップグレードの準備をして Windows アップグレードを管理](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness)する」を参照してください。詳細については、「アップグレードの準備状況」をご覧ください。

次に、ガイドに従って構成マネージャー (Current Branch) を使用して、Windows 7 以降のオペレーティングシステムを Windows 10 にアップグレードします。 高リスク展開の場合と同様に、先に進む前にユーザーデータをバックアップすることをお勧めします。 OneDrive クラウドストレージは、Microsoft 365 ユーザーのライセンスを使用する準備が整っており、そのファイルを安全に保存するために使用できます。 詳細については、「 [OneDrive クイックスタートガイド](https://aka.ms/ODfBquickstartguide)」を参照してください。 このページにアクセスするには、Office 365 または Microsoft 365 テナントのテナント管理者またはグローバル管理者としてサインインする必要があります。

Configuration Manager のバージョンと、対応する Windows 10 クライアントのバージョンの一覧については、「 [Configuration manager の windows 10 のサポート](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10)」を参照してください。

**Windows のアップグレードの準備状況を確認するには**

Windows 10 の展開を開始する前に、これらの要件を確認します。

- **アップグレード対象となる windows エディション**-デバイスでは、windows 7 または windows 8.1 のエディションを実行している必要があります。これは、Windows 10 Enterprise へのアップグレードに適しています。 サポートされているエディションの一覧については、「 [Windows 10 のアップグレードパス](https://aka.ms/win10upgradepaths)」を参照してください。 
- **サポート**されるデバイス-windows 8.1 と互換性のあるほとんどのコンピューターは、windows 10 と互換性があります。 デバイスが適切に機能するには、更新されたドライバーを Windows 10 にインストールする必要がある場合があります。 詳細については、「 [Windows 10 の仕様](https://aka.ms/windows10specifications)」を参照してください。
- **展開の準備**-展開の構成を開始する前に、次のことを確認してください。
    - Windows 10 インストールメディア-インストールメディアは、ISO が既にマウントされている別のドライブに配置する必要があります。 ISO は、 [MSDN サブスクライバーダウンロード](https://aka.ms/msdn-subscriber-downloads)から入手することも、[ボリュームライセンスサービスセンター](https://aka.ms/mvlsc)から入手することもできます。
    - ユーザーデータのバックアップ-ユーザーデータはアップグレードに移行されますが、バックアップシナリオを構成することをお勧めします。 たとえば、すべてのユーザーデータを OneDrive アカウントにエクスポートし、BitLocker から Go に暗号化された USB フラッシュドライブ、またはネットワークファイルサーバーをエクスポートします。 詳細については、「 [Windows でデータをバックアップまたは転送](https://aka.ms/backuptransferdatawindows)する」を参照してください。
- **環境の準備**-既存の Configuration Manager サーバー構造を使用して、オペレーティングシステムの展開を準備します。 構成マネージャー環境では、基本設定に加えて、次の構成を行う必要があります。
    1. [Active Directory スキーマを拡張](https://aka.ms/extendadschema)し、 [System Management コンテナーを作成](https://aka.ms/createsysmancontainer)します。
    2. Active Directory フォレストの探索と Active Directory システムの検出を有効にします。 詳細については、「 [Configure discovery メソッド For Configuration Manager](https://aka.ms/configurediscoverymethods)」を参照してください。
    3. コンテンツおよびサイト割り当ての IP 範囲の境界と境界グループを作成します。 詳細については、「 [Configuration Manager のサイト境界と境界グループを定義する](https://aka.ms/definesiteboundaries)」を参照してください。
    4. Configuration Manager reporting services ポイントの役割を追加して構成します。 詳細については、「 [Configuration Manager でレポートを構成する](https://aka.ms/configurereporting)」を参照してください。
    5. パッケージ用のファイルシステムフォルダー構造を作成します。
    6. パッケージ用の Configuration Manager コンソールフォルダー構造を作成します。
    7. 構成マネージャー (現在のブランチ) 更新プログラムと追加の Windows 10 前提条件をインストールします。

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a>パート 2: 構成マネージャーを使用して Windows 10 OS イメージを追加する
ここで、完全な Windows 10 インストールメディアを含むオペレーティングシステムアップグレードパッケージを作成する必要があります。 次の手順では、Configuration Manager を使用して Windows 10 Enterprise x64 のアップグレードパッケージを作成します。

**構成マネージャーを使用して Windows 10 OS イメージを追加するには**

1. Configuration Manager コンソールを使用して、[**ソフトウェアライブラリ**] ワークスペースの [**オペレーティングシステムのアップグレード**パッケージ] ノードを右クリックし、[**オペレーティングシステムアップグレードパッケージの追加**] を選択します。
2. [**データソース**] ページで、Windows 10 Enterprise x64 メディアへの UNC パスを指定し、[**次へ**] を選択します。
3. [**全般**] ページで、 **Windows 10 Enterprise x64 Upgrade**を指定し、[**次へ**] を選択します。 
4. [**概要**] ページで、[**次へ**] を選択し、[**閉じる**] を選択します。 
5. 作成した**Windows 10 Enterprise X64 更新プログラム**パッケージを右クリックして、[**コンテンツの配布**] を選択します。 
6. 配布ポイントを選択します。

## <a name="part-3-configure-deployment-settings"></a>パート 3: 展開設定を構成する
この手順では、Windows 10 アップグレードの設定を含むアップグレードタスクシーケンスを構成します。 次に、アップグレードするデバイスを特定し、それらのデバイスにタスクシーケンスを展開します。

### <a name="create-a-task-sequence"></a>タスクシーケンスを作成する
アップグレードタスクシーケンスを作成するには、次の手順を実行します。
  
1. 構成マネージャーコンソールの [**ソフトウェアライブラリ**] ワークスペースで、[**オペレーティングシステム**] を展開します。 
2. [**タスク**シーケンス] ノードを右クリックし、[**タスクシーケンスの作成**] を選択します。
3. [**タスクシーケンスの新規作成**] ページで、[**アップグレードパッケージからのオペレーティングシステムのアップグレード**] を選択し、[**次へ**] を選択します。
4. [**タスクシーケンス情報**] ページで、 **Windows 10 Enterprise x64 Upgrade**を指定し、[**次へ**] を選択します。
5. [ **Windows オペレーティングシステムのアップグレード**] ページで、 **[参照**] を選択して、 **windows 10 Enterprise x64 アップグレードオペレーティングシステムアップグレードパッケージ**を選択し、[ **OK**] を選択して、[**次へ**] を選択します。
6. 残りのウィザードページを続けて、[**閉じる**] を選択します。

### <a name="create-a-device-collection"></a>デバイスコレクションを作成する
アップグレードタスクシーケンスを作成した後、アップグレードするデバイスを含むコレクションを作成する必要があります。

> [!NOTE]
> 次の設定を使用して、単一のデバイスで展開をテストします。 準備が整ったら、さまざまなメンバーシップルールを使用してデバイスのグループを含めることができます。 詳細については、「 [Configuration Manager でコレクションを作成する方法](https://docs.microsoft.com/configmgr/core/clients/manage/collections/create-collections)」を参照してください。

1. 構成マネージャーコンソールの [**アセットとコンプライアンス**] ワークスペースで、[**デバイスコレクション**] を右クリックし、[**デバイスコレクションの作成**] を選択します。 
2. [デバイスコレクションの作成] ウィザードの **[全般**] ページで、次の設定を入力し、[**次へ**] を選択します。
    - Name: Windows 10 Enterprise x64 アップグレード
    - コレクションを制限する: すべてのシステム
3. [**メンバーシップの規則**] ページで、[**ルール** > の**直接ルール**の追加] を選択して、[ダイレクトメンバーシップの規則の作成] ウィザードを起動します。
4. [ダイレクトメンバーシップルールの作成] ウィザードの [**ようこそ**] ページで、[**次へ**] を選択します。
5. [**リソースの検索**] ページで、次の設定を入力します。プレースホルダーの**値**のテキストは、アップグレードするデバイスの名前に置き換えます。 
    - リソースクラス: システムリソース
    - 属性名: Name
    - 値: *PC0003*
6. [**リソースの選択**] ページで、デバイスを選択し、[**次へ**] を選択します。
7. [ダイレクトメンバーシップの規則の作成] ウィザードと [デバイスコレクションの作成] ウィザードを完了します。  
8. Windows 10 Enterprise x64 アップグレードコレクションを確認します。 コレクションに追加したコンピューターが表示されるまで、処理を続行しないでください。

### <a name="create-an-operating-system-deployment"></a>オペレーティングシステムの展開を作成する
タスクシーケンスの展開を作成するには、次の手順を実行します。

1. 構成マネージャーコンソールの [**ソフトウェアライブラリ**] ワークスペースで、前の手順で作成したタスクシーケンスを右クリックし、[**展開**] を選択します。
2. [**全般**] ページで、 **Windows 10 Enterprise x64 アップグレード**コレクションを選択し、[**次へ**] を選択します。
3. [**コンテンツ**] ページで、[**次へ**] を選択します。
4. [**展開の設定**] ページで、次の設定を選択し、[**次へ**] を選択します。

    > [!NOTE]
    > このテスト展開では、目的を**利用可能**に設定します。これにより、展開を開始するためにユーザーの介入が必要になります。 運用環境では、必要な目的を使用して展開を自動化することができます。これには、展開の実行時のスケジュール設定など、追加のオプションの構成が含まれます。 

    - アクション: Install
    - 目的: 利用可能

5. [**スケジュール**] ページで、既定の設定をそのまま使用し、[**次へ**] を選択します。
6. [**ユーザーの作業**] ページで、既定の設定をそのまま使用し、[**次へ**] を選択します。
7. [**通知**] ページで、既定の設定をそのまま使用し、[**次へ**] を選択します。
8. [**概要**] ページで、[**次へ**] を選択し、[**閉じる**] を選択します。

## <a name="part-4-start-the-windows-10-upgrade-task-sequence"></a>パート 4: Windows 10 のアップグレードタスクシーケンスを開始する
アップグレードするデバイスで Windows 10 のアップグレードタスクシーケンスを開始するには、次の手順を実行します。
 
1. Windows コンピューターにログオンし、**ソフトウェアセンター**を起動します。
2. 前の手順で作成したタスクシーケンスを選択し、[**インストール**] を選択します。
3. タスクシーケンスが開始されると、必要なコマンドラインパラメーターを指定して Windows セットアッププログラム (Setup.exe) を起動することによって、一括アップグレードプロセスが自動的に開始されます。これにより、すべてのデータ、設定、アプリ、およびドライバ.
4. タスクシーケンスが正常に完了すると、コンピューターは Windows 10 に完全にアップグレードされます。

エンタープライズ環境で Windows 10 を使用するときに問題が発生した場合、「[最も一般的な問題に対する上位の Microsoft サポート ソリューション](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)」 を参照してください。これらのリソースには、サポート技術情報の記事、更新情報、およびライブラリの記事が含まれます。

組織全体で更新プログラムをロールアウトする際には、Windows Analytics の更新プログラムのコンプライアンス機能を使用して、Windows 10 デバイスの OS 更新プログラムのコンプライアンス、展開の進行状況、およびエラーのトラブルシューティングの全体的なビューを提供します。 この新しいサービスは、インストールの進行状況、Windows 更新プログラムの構成、その他の情報を含む診断データを使用して、そのような洞察を追加のコストや追加のインフラストラクチャ要件を伴わずに提供します。 Business またはその他の管理ツール用の Windows Update で使用されているかどうかにかかわらず、デバイスが適切に更新されることを保証できます。

詳細については、「 [windows の更新プログラムの監視」および「更新プログラムのコンプライアンスを使用した Windows Defender ウイルス対策](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor)」を参照し、更新プログラムのコンプライアンスをご確認ください。

中間チェックポイントとして、この手順に対応する[終了条件](windows10-exit-criteria.md#crit-windows10-step2)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![手順 3](./media/stepnumbers/Step3.png)| [Windows Autopilot を使用して新しいデバイスに Windows 10 Enterprise を展開する](windows10-deploy-autopilot.md) |
