---
title: Windows Autopilot を使用して新しいデバイスに Windows 10 Enterprise を展開する
description: Windows Autopilot を使用して Windows 10 Enterprise を構成および展開するためのガイダンスです。
keywords: Microsoft 365、Microsoft 365 Enterprise、Microsoft 365 ドキュメント、Windows 10 Enterprise、展開、Windows Autopilot
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: e5e3e4fb48a0eb2af1978cbd5a687c67c72bea0c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596644"
---
# <a name="step-3-deploy-windows-10-enterprise-for-new-devices-with-windows-autopilot"></a>手順 3: Windows Autopilot を使用して新しいデバイスに Windows 10 Enterprise を展開する

*この記事は、Microsoft 365 Enterprise の E3 および E5 の両バージョンに適用されます*

![フェーズ 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

新しい Windows 10 PC では、Windows Autopilot を使用して、組織の OOBE (out-of-box-experience) をカスタマイズし、すでに構成されているアプリや設定を使用して新しいシステムを展開できます。イメージの展開や挿入するドライバー、管理するインフラストラクチャはありません。各ユーザーは IT 管理者に問い合わせる必要なく、展開プロセスを個別に実行することができます。

Windows Autopilot を使用して、新しい Windows 10 デバイスをセットアップして事前構成し、使用準備を整えることができます。Windows Autopilot の利点やシナリオについての詳細情報は、「[Windows Autopilot の概要](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot)」を参照してください。準備が完了したら、次のパートに従って設定を開始します。

## <a name="the-windows-autopilot-deployment-process-poster"></a>Windows 自動操縦の展開プロセスのポスター

Windows 自動操縦ポスターは、縦置きモード (11x17) の2ページです。 ブラウザーに PDF を表示するには、以下の画像をクリックします。 

[![Autopilot ポスターを使用した Windows 10 の展開](./media/windows10-deploy-autopilot/windows10-autopilot-flowchart.png)](https://docs.microsoft.com/windows/deployment/media/Windows10AutopilotFlowchart.pdf)

このポスターを [PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10AutopilotFlowchart.pdf) または [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10Autopilotflowchart.vsdx) 形式でダウンロードすることもできます。

## <a name="part-1-start-windows-autopilot-deployment"></a>パート 1: Windows Autopilot 展開を開始する
「[Windows Autopilot の概要](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot)」を参照して、次のようにします。

1. Windows Autopilot 展開についての詳細情報を参照し、前提条件を完了します。前提条件は以下のとおりです。
    - **デバイスの登録と OOBE のカスタマイズ**

        デバイスを登録するには、ハードウェア ID を取得し、それを登録する必要があります。Microsoft はさまざまなハードウェア ベンダーと協力して、必要な情報をユーザーに提供したり、ユーザーの代わりにアップロードしたりできるよう積極的に取り組んでいます。また、デバイスのハードウェア ID を CSV ファイルに生成する PowerShell スクリプトを使用してこの情報を自分で取得することもできます。

        デバイスを登録すると、プライバシーの設定や使用許諾契約書をスキップするなどの、OOBE のカスタマイズ オプションを構成できます。

    - **OOBE の企業ブランド化**

        これにより、デバイス OOBE 中に表示するブランドを追加することができます。

    - **Microsoft Intune での MDM の自動登録**
        
        自動登録では、ユーザーが自分の Windows 10 デバイスを Azure AD に接続するときに、Intune のに登録してデバイス管理を行うことができます。登録するには、個人用デバイスに職場アカウントを追加するか、企業が所有するデバイスを Azure AD に参加させます。バックグラウンドでは、デバイスが Intune で管理ができるように登録されます。

    - **Windows Autopilot で使用するクラウド サービスへのネットワーク接続**

        Windows Autopilot 展開プログラムは、多数のクラウド サービスを使用してデバイスを準備完了の状態にするため、Windows Autopilot デバイスとして登録されたデバイスからそれらのサービスにアクセスできる必要があります。 

    - **デバイスに Windows 10 バージョン 1703 以降がプレインストールされている必要がある**

2. Windows Autopilot 展開プログラムについての詳細を参照し、組織に最適な展開プログラムを選択します。次の展開プログラムから選択できます。
    - **ビジネス向け Microsoft Store**
    - **Microsoft Intune**
    - **パートナー センター**

## <a name="part-2-set-up-a-windows-10-device-for-microsoft-365"></a>パート 2: Microsoft 365 向け Windows 10 デバイスのセットアップ
Microsoft 365 ユーザーに Windows デバイスを設定する前に、すべての Windows デバイスが Windows 10 バージョン 1703 (Creators Update) 以降を使用していることを確認してください。

組織内のすべての Windows デバイスが Windows 10 Creators Update に更新された後、またはすでに Windows 10 Creators Updat を使用している場合、これらのデバイスを組織の Azure Active Directory に参加させることができます。

### <a name="set-up-a-brand-new-or-newly-upgraded-windows-10-device"></a>新しい、または新しくアップグレードした Windows 10 デバイスのセットアップ
Windows 10 Creators Update 以降を使用している新しいデバイス、または Windows 10 Creators Update 以降にアップグレードしたけれども OOBE 設定をしなかったデバイスで、Windows 10 OOBE を使用してデバイスをセットアップするには以下の手順に従ってください。

1. ワイヤレス ネットワークが構成されていない場合は、有線接続またはイーサネット接続を使用してデバイスをインターネットに接続してください。
2. Windows デバイスのセットアップを行います。新規またはリセットされたデバイスで、[**お住まいの地域はこちらでよろしいですか?**] 画面から始まります。
3. Windows 10 デバイスのセットアップを続け、[**設定する方法を指定してください。**] のページまで進みます。ここで、[**組織用に設定**] を選択します。
4. Microsoft 365 ユーザーのアカウントとパスワードでサインインします。ユーザー パスワードの設定によっては、パスワードの更新を求められる場合があります。 
5. Windows 10 デバイスのセットアップを完了します。

完了後、デバイスは組織の Azure AD に接続します。

### <a name="set-up-a-device-that-has-already-completed-out-of-box-setup"></a>OOBE セットアップが完了しているデバイスの設定
デバイスで Windows 10 Creators Update (またはそれ以降) を使用していて、OOBE セットアップを完了している場合は、次の手順に従ってください。

1. Windows 10 バージョン 1703 (Creators Update) を使用しているユーザーの Windows PC で、[**Windows**] ロゴを選択し [**設定**] アイコンを選びます。
2. [**設定**] で、[**アカウント**] に移動します。
3. [**情報**] ページで、[**職場または学校にアクセス**]  >  [**接続**] を選択します。
4. [**職場または学校アカウントの設定**] ダイアログ ボックスの [**ほかの操作**] の下にある、[**このデバイスを Azure Active Directory に参加させる**] をクリックします。
5. [**サインインしましょう**] ページで、職場または学校のアカウントを入力し、[**次へ**] を選択します。
6. [**パスワードの入力**] ページで、パスワードを入力し、[**サインイン**] を選択します。
7. [**組織の確認**] ページの情報が正しいことを確認し、[**参加**] を選択します。
8. [**準備が完了しました!**] ページで、[**完了**] を選択します。

完了後、ユーザーが組織の Azure AD に接続されます。

### <a name="verify-the-device-is-connected-to-azure-ad"></a>デバイスが Azure AD に接続されていることを確認する
Azure AD で、デバイスの同期状態を確認し、デバイス上で Microsoft 365 アカウントの使用を開始するには次の手順に従います。 

1. [**設定**] を開きます。
2. [**職場または学校にアクセス**] ページで、[**<organization name>に接続**] を選択し、[**情報**] および [**切断**] ボタンを表示します。
3. [**情報**] を選択すると、同期状態が表示されます。
4. [**同期の状態**] ページで [**同期**] を選択すると、最新のモバイル デバイス管理ポリシーを PC に取得することができます。
5. Microsoft 365 アカウントを使用するには、Windows の [**スタート**] ボタンをクリックし、現在のアカウントの画像を右クリックし、[ユーザーの**切り替え**] を選択します。
6. 組織のメール アドレスとパスワードを使用してサインインします。

エンタープライズ環境で Windows 10 を使用するときに問題が発生した場合、「[最も一般的な問題に対する上位の Microsoft サポート ソリューション](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)」 を参照してください。これらのリソースには、サポート技術情報の記事、更新情報、およびライブラリの記事が含まれます。

中間チェックポイントとして、この手順に対応する[終了条件](windows10-exit-criteria.md#crit-windows10-step3)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![手順 4](./media/stepnumbers/Step4.png)| [デバイスの正常性とコンプライアンスを監視する](windows10-enable-windows-analytics.md) |
