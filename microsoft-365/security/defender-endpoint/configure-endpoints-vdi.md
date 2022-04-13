---
title: 非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード
description: 構成パッケージを仮想デスクトップ インフラストラクチャ (VDI) デバイスにデプロイして、サービスにオンボードMicrosoft Defender for Endpoint。
keywords: 仮想デスクトップ インフラストラクチャ (VDI) デバイス、VDI、デバイス管理の構成、Microsoft Defender for Endpointの構成、エンドポイント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.date: 02/14/2022
ms.technology: mde
ms.openlocfilehash: fe86b09588f08a05183de146092b50b5cb530d0e
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2022
ms.locfileid: "64825016"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-in-microsoft-365-defender"></a>Microsoft 365 Defenderで非永続的仮想デスクトップ インフラストラクチャ (VDI) デバイスをオンボードする

仮想デスクトップ インフラストラクチャ (VDI) は、エンド ユーザーがほぼすべてのデバイス (パーソナル コンピューター、スマートフォン、タブレットなど) からエンタープライズ仮想デスクトップ インスタンスにアクセスできるようにする IT インフラストラクチャの概念であり、組織がユーザーに物理マシンを提供する必要がなくなります。 VDI デバイスを使用すると、IT 部門が物理エンドポイントの管理、修復、交換を行わなくなったため、コストが削減されます。 承認されたユーザーは、セキュリティで保護されたデスクトップ クライアントまたはブラウザーを使用して、承認された任意のデバイスから同じ会社のサーバー、ファイル、アプリ、サービスにアクセスできます。

IT 環境の他のシステムと同様に、高度な脅威や攻撃から保護するために、エンドポイントの検出と応答 (EDR) とウイルス対策ソリューションも用意されている必要があります。


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- 仮想デスクトップ インフラストラクチャ (VDI) デバイス
- Windows 10、Windows 11、Windows Server 2019、Windows Server 2022、Windows Server 2008R2/2012R2/2016

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configvdi-abovefoldlink)

 > [!NOTE]
  > **永続的な VDI** - [永続的な VDI マシンを](configure-endpoints.md)Microsoft Defender for Endpointにオンボードする方法は、デスクトップやノート PC などの物理マシンをオンボードする場合と同じように処理されます。 グループ ポリシー、Microsoft エンドポイント マネージャー、およびその他の方法を使用して、永続的なマシンをオンボードできます。 Microsoft 365 Defender ポータルで (https://security.microsoft.com)オンボーディングの下で、優先するオンボード方法を選択し、その種類の指示に従います。 

## <a name="onboarding-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>非永続的仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード

Defender for Endpoint では、非永続的な VDI セッションオンボードがサポートされます。

VDI インスタンスのオンボード時に、関連する課題が発生する可能性があります。 このシナリオの一般的な課題は次のとおりです。

- 短時間のセッションの即時早期オンボード。これは、実際のプロビジョニングの前に Defender for Endpoint にオンボードする必要があります。
- 通常、デバイス名は新しいセッションに再利用されます。

VDI 環境では、VDI インスタンスの有効期間が短い場合があります。 VDI デバイスは、次のいずれかの方法で Defender for Endpoint ポータルに表示できます。


- VDI インスタンスごとに 1 つのポータル エントリ。 VDI インスタンスが既にMicrosoft Defender for Endpointにオンボードされていて、ある時点で削除された後、同じホスト名で再作成された場合、この VDI インスタンスを表す新しいオブジェクトはポータルに作成されません。 


  > [!NOTE]
  > この場合、無人応答ファイルを使用するなど、セッションの作成時に *同じ* デバイス名を構成する必要があります。

- デバイスごとに複数のエントリ (VDI インスタンスごとに 1 つ)。

次の手順では、VDI デバイスのオンボードについて説明し、1 つまたは複数のエントリの手順を強調表示します。

> [!WARNING]
> リソース構成が低い環境では、VDI ブート手順によって Defender for Endpoint センサーのオンボードが遅くなる可能性があります。

### <a name="for-windows-10-or-windows-11-or-windows-server-2012-r2-and-later"></a>Windows 10、Windows 11、または R2 以降Windows Server 2012

> [!NOTE]
> この機能を機能させるには、まずオンボード Windows サーバーの手順を使用してインストール パッケージを適用して[、Windows Server 2016とWindows Server 2012](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2012-r2-and-windows-server-2016) R2 を準備する必要があります。

1.  サービス オンボード ウィザードからダウンロードした VDI 構成パッケージ .zip ファイル (*WindowsDefenderATPOnboardingPackage.zip*) を開きます。 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>からパッケージを取得することもできます。

    1. ナビゲーション ウィンドウで、**設定** > **EndpointsDevice** >  **managementOnboarding** >  を選択します。

    1. オペレーティング システムを選択します。

    1.  **[展開方法]** フィールドで、**非永続的エンドポイントの VDI オンボード スクリプトを選択します**。

    1. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

2. .zip ファイルから抽出された WindowsDefenderATPOnboardingPackage フォルダーから、パス `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`の下のゴールデン/マスター イメージにファイルをコピーします。
    1. デバイスごとに複数のエントリ (セッションごとに 1 つずつ) を実装する場合は、WindowsDefenderATPOnboardingScript.cmd をコピーします。
    2. デバイスごとに 1 つのエントリを実装する場合は、Onboard-NonPersistentMachine.ps1と WindowsDefenderATPOnboardingScript.cmd の両方をコピーします。

    > [!NOTE]
    > フォルダーが表示 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` されない場合は、非表示になっている可能性があります。 [**非表示のファイルとフォルダーを表示** する] オプションをエクスプローラーから選択する必要があります。

3. [ローカル グループ ポリシー エディター] ウィンドウを開き、[**コンピューターの構成****] Windows 設定** \> **[スクリプト** \> **のスタートアップ]**\> に移動します。

   > [!NOTE]
   > ドメイン グループ ポリシーは、非永続的 VDI デバイスのオンボードにも使用できます。

4. 実装するメソッドに応じて、適切な手順に従います。
    - デバイスごとに 1 つのエントリの場合:

         **[PowerShell スクリプト**] タブを選択し、[**追加**] をクリックします (Windows エクスプローラーは、オンボード スクリプトを先にコピーしたパスで直接開きます)。 PowerShell スクリプトのオンボードに移動します `Onboard-NonPersistentMachine.ps1`。 自動的にトリガーされるため、他のファイルを指定する必要はありません。

    - デバイスごとに複数のエントリの場合:

         [**スクリプト**] タブを選択し、[**追加**] をクリックします (Windows エクスプローラーは、オンボード スクリプトを先にコピーしたパスで直接開きます)。 オンボード bash スクリプトに移動します `WindowsDefenderATPOnboardingScript.cmd`。

5. ソリューションをテストします。
   1. 1 つのデバイスでプールを作成します。
   2. デバイスにログオンします。
   3. デバイスからログオフします。
   4. 別のユーザーと一緒にデバイスにログオンします。
   5. 実装するメソッドに応じて、適切な手順に従います。
      - デバイスごとに 1 つのエントリの場合: ポータルで 1 つのエントリのみを確認Microsoft 365 Defender。
      - デバイスごとに複数のエントリの場合: ポータルで複数のエントリMicrosoft 365 Defender確認します。

6. ナビゲーション ウィンドウで [ **デバイス] の一覧** をクリックします。

7. デバイス名を入力して検索機能を使用し、検索の種類として **[デバイス** ] を選択します。

## <a name="for-downlevel-skus-windows-server-2008-r2"></a>ダウンレベル SKU の場合 (Windows Server 2008 R2)

> [!NOTE]
> 他のWindows サーバー バージョンのこれらの手順は、MMA を必要とするWindows Server 2016およびWindows Server 2012 R2 に対して前のMicrosoft Defender for Endpointを実行している場合にも適用されます。 新しい統合ソリューションに移行する手順は、「[Microsoft Defender for Endpoint のサーバー移行シナリオ](/microsoft-365/security/defender-endpoint/server-migration)」 にあります。

> [!NOTE]
> 次のレジストリは、目的が "デバイスごとに 1 つのエントリ" を達成する場合にのみ関連します。

1. レジストリ値を次に設定します。

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    またはコマンド ラインを使用する:

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. サーバーの [オンボード プロセスに](configure-server-endpoints.md)従います。 

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>非永続的仮想デスクトップ インフラストラクチャ (VDI) イメージの更新

VDI で実行されている VM に更新プログラムを簡単にデプロイする機能を使用して、このガイドを短縮し、コンピューターで迅速かつ簡単に更新プログラムを入手する方法に焦点を当てています。 更新プログラムがホスト サーバー上のコンポーネント ビットに展開され、オンになると VM に直接ダウンロードされるため、ゴールデン イメージを定期的に作成してシールする必要はなくなりました。

詳細については、「[仮想デスクトップ インフラストラクチャ (VDI) 環境でのMicrosoft Defender ウイルス対策のデプロイ ガイド」のガイダンスに](/security/defender-endpoint/deployment-vdi-microsoft-defender-antivirus)従ってください。


## <a name="related-topics"></a>関連項目
- [グループ ポリシーを使用してデバイスをオンボードする](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager を使用した Windows デバイスのオンボード](configure-endpoints-sccm.md)
- [モバイル デバイス管理ツールを使用した Windows デバイスのオンボード](configure-endpoints-mdm.md)
- [ローカル スクリプトを使用した Windows デバイスのオンボード](configure-endpoints-script.md)
- [Microsoft Defender for Endpoint の問題のトラブルシューティング](troubleshoot-onboarding.md)
