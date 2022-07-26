---
title: Microsoft Defender for Business 試用版プレイブック
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: article
ms.collection: m365-security-compliance
ms.localizationpriority: high
ms.prod: m365-security
ms.technology: mdb
search.appverid:
- MOE150
- MET150
description: このプレイブックを参考に、Defender for Business の試用版を最大限にご活用ください。 すぐに設定し、新しいセキュリティ機能をご使用いただけます。
ms.custom: trial-playbook
ms.openlocfilehash: 16843ef3dcb2efe36f9102001fe5579e920287b4
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2022
ms.locfileid: "66994625"
---
# <a name="trial-playbook-microsoft-defender-for-business"></a>試用版プレイブック: Microsoft Defender for Business

**Defender for Business 試用版プレイブックへようこそ!**

このプレイブックは、30 日間の無料試用版を最大限に活用するための簡単なガイドです。 この資料に記載されている Microsoft Defender チームからの推奨事項と共に、Defender for Business で従来のウイルス対策保護から次世代の保護、エンドポイントの検出と対応、そして脅威と脆弱性の管理へとセキュリティを強化する方法をご覧ください。

## <a name="what-is-defender-for-business"></a>Defender for Business とは

Defender for Business は、中小企業 (最大 300 人の従業員) 向けに特別に設計された新しいエンドポイント セキュリティ ソリューションです。 このエンドポイント セキュリティ ソリューションを使用すると、組織のデバイスがランサムウェア、マルウェア、フィッシング、その他の脅威から適切に保護されます。

:::image type="content" source="media/mdb-offering-overview.png" alt-text="Defender for Business の機能。":::

**では、始めましょう。**

## <a name="set-up-your-trial"></a>試用版のセットアップ

試用版サブスクリプションの設定方法は次のとおりです。

1. [ユーザーを追加してライセンスを割り当てる](#step-1-add-users-and-assign-licenses)。
2. [Microsoft 365 Defender ポータルにアクセスする](#step-2-visit-the-microsoft-365-defender-portal)。
3. [セットアップ ウィザードを使用する](#step-3-use-the-setup-wizard-in-defender-for-business-recommended)。
4. [Defender for Business のセットアップと構成を行う](#step-4-set-up-and-configure-defender-for-business)。

### <a name="step-1-add-users-and-assign-licenses"></a>手順 1: ユーザーを追加してライセンスを割り当てる

Defender for Business にサインアップした後の初めの手順は、**[ユーザーの追加とライセンスの割り当て](mdb-add-users.md)** です。

> [!NOTE]
> この手順を実行するには、全体管理者である必要があります。 既定では、会社を代表して Microsoft 365 または Defender for Business にサインアップしたユーザーが、全体管理者となります。 [役割とアクセス許可に関する詳細を学ぶ](mdb-roles-permissions.md)。

### <a name="step-2-visit-the-microsoft-365-defender-portal"></a>手順 2: Microsoft 365 Defender ポータルにアクセスする
 
Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) は、Defender for Business を使用および管理できるワンストップ ポータルです。 このポータルには、使用を開始するのに役立つ吹き出し、関連情報を表示するカード、さまざまな機能に簡単にアクセスできるナビゲーション バーなどがあります。

- **[Microsoft 365 Defender ポータルにアクセスする](mdb-get-started.md)**。
- 画面の左側にある **[ナビゲーション バーで](mdb-get-started.md#the-navigation-bar)**、インシデントへのアクセス、レポートの表示、セキュリティ ポリシーと設定の管理を行います。

### <a name="step-3-use-the-setup-wizard-in-defender-for-business-recommended"></a>手順 3: Defender for Business のセットアップ ウィザードを使用する (推奨)

Defender for Business は、中小企業の時間と労力を節約できるよう設計されています。 初期のセットアップと構成は、セットアップ ウィザードを使用して行えます。 セットアップ ウィザードを使用すると、セキュリティ チームへのアクセス権の付与、セキュリティ チームのメール通知の設定、会社の Windows デバイスのオンボードが行えます。 **[セットアップ ウィザードを使用する](mdb-use-wizard.md)**。

> [!NOTE]
> セットアップ ウィザードは 1 回だけ使用できます。

#### <a name="setup-wizard-flow-what-to-expect"></a>セットアップ ウィザードの使用の流れ

> [!TIP]
> **セットアップ ウィザードの使用は省略可能です。** (「[ウィザードを使用しない場合](mdb-use-wizard.md#what-happens-if-i-dont-use-the-wizard)」を参照してください) ウィザードを使用しない場合、またはセットアップ プロセスが完了する前にウィザードを閉じた場合は、手動でセットアップと構成プロセスを完了させることができます。 [手順 4](#step-4-set-up-and-configure-defender-for-business) を参照してください。 

1. **[ユーザーにアクセス許可を割り当てる](mdb-roles-permissions.md#view-or-edit-role-assignments)**。 セキュリティ チームに Microsoft 365 Defender ポータルへのアクセスを許可します。

2. セキュリティ チームの **[メール通知を設定する](mdb-email-notifications.md#view-and-edit-email-notifications)**。

3. **[Windows デバイスをオンボードして構成する](mdb-onboard-devices.md)**。 デバイスをすぐにオンボードすると、初日からそれらのデバイスを保護できます。

   > [!NOTE]
   > セットアップ ウィザードを使用すると、Intune に既に登録されている Windows デバイスがあるかどうかが検出されます。 検出されたデバイスのすべて、または一部に対して自動オンボードを使用するかどうかを確認するメッセージが表示されます。 すべての Windows デバイスを一度にオンボードすることも、最初に特定のデバイスを選択して、後で他のデバイスを追加することもできます。 [自動オンボードの詳細について学ぶ](mdb-use-wizard.md#what-is-automatic-onboarding)。
   
   他のデバイスをオンボードするには、[手順 4](#step-4-set-up-and-configure-defender-for-business) を参照してください。

4.  **[セキュリティ ポリシーの表示と編集](mdb-configure-security-settings.md)**。 Defender for Business には、会社のデバイスに適用し、次世代の保護とファイアウォール保護を実現する既定のセキュリティ ポリシーが搭載されています。 これらの事前構成済みセキュリティ ポリシーには推奨設定が使用されているため、デバイスが Defender for Business にオンボードされた時点ですぐに保護されます。 また、ポリシーを編集したり、新しいポリシーを作成したりすることもできます。

### <a name="step-4-set-up-and-configure-defender-for-business"></a>手順 4: Defender for Business のセットアップと構成を行う

セットアップ ウィザードを使用しない場合は、Defender for Business の[全体的なセットアップと構成プロセス](mdb-setup-configuration.md#the-setup-and-configuration-process)を示した次のダイアグラムを参照してください。

[:::image type="content" source="media/mdb-setup-process-2.png" alt-text="Defender for Business.のセットアップと構成プロセス。":::](mdb-setup-configuration.md)

セットアップ ウィザードを使用した後に、Windows 以外のデバイスなど、他のデバイスをオンボードする必要がある場合は、次の手順の手順 4 に直接進んでください。

1. Defender for Business を構成して使用するための **[要件を確認](mdb-requirements.md)** する。 

2. Microsoft 365 Defender ポータルで、**[役割とアクセス許可を割り当てる](mdb-roles-permissions.md)**。

   - [Defender for Business の役割について学ぶ](mdb-roles-permissions.md#roles-in-defender-for-business)。 
   - [セキュリティ チームの役割の割り当てを表示または編集する](mdb-roles-permissions.md#view-or-edit-role-assignments)。

3. セキュリティ チームの **[メール通知を設定する](mdb-email-notifications.md)**。

   - [メール通知の種類について学ぶ](mdb-email-notifications.md#types-of-email-notifications)。
   - [メール通知設定の表示と編集](mdb-email-notifications.md#view-and-edit-email-notifications)。

4. **[デバイスのオンボード](mdb-onboard-devices.md)**。 Defender for Business では、会社のデバイスをオンボードするうえでいくつかの方法があります。 まず、オンボードするオペレーティング システムを選択します。

   | デバイスのタイプ | オンボード方法 |
   |:---|:---|
   | [Windows クライアント](mdb-onboard-devices.md) | Windows クライアント デバイスを Defender for Business にオンボードするには、次のいずれかのオプションを選択します。<ul><li>ローカル スクリプト (Microsoft 365 Defender ポータルでデバイスを手動でオンボードする場合)</li><li>グループ ポリシー (既に グループ ポリシー を使用していて、この方法を使用する場合)</li><li>Microsoft Intune (*推奨*、[Microsoft 365 Business Premium](../../business-premium/index.md) に含まれています)</li></ul> |
   | [Mac](mdb-onboard-devices.md) | Mac をオンボードするには、次のいずれかの方法があります。<ul><li>Mac 用ローカル スクリプト (*推奨*)</li><li>Microsoft Intune for Mac (Intune は [Microsoft 365 Business Premium](../../business-premium/index.md) に含まれています)</li></ul><p>Mac をオンボードするには、ローカル スクリプトの使用をお勧めします。 [Intune でも Mac デバイスの登録](/mem/intune/enrollment/macos-enroll)はできますが、ローカル スクリプトが Mac を Defender for Business にオンボードするための最も簡単な方法です。 |
   | Windows Server および Linux Server | *Windows Server または Linux Server のインスタンスをオンボードする機能は現在プレビュー段階であり、追加のライセンスが必要です*。 詳細については、次の記事を参照してください。 <ul><li>[Defender for Business の要件](mdb-requirements.md)</li><li>[Defender for Business へのデバイスのオンボード](mdb-onboard-devices.md)</li></ul> |
   | [モバイル デバイス](mdb-onboard-devices.md) | Android や iOS/iPadOS などのモバイル デバイスをオンボードするには、Microsoft Intuneが必要です。 [Microsoft 365 Business Premium](../../business-premium/index.md) をご使用の場合、Intune はサブスクリプションに含まれています。 また、個別に購入することもできます。 これらのデバイスを Intune に登録する方法については、次のリソースを参照してください。<ul><li>[Android デバイスを登録する](/mem/intune/enrollment/android-enroll)</li><li>[iOS または iPadOS デバイスを登録する](/mem/intune/enrollment/ios-enroll)</li></ul> |

5. **[セキュリティ ポリシーの確認と構成](mdb-configure-security-settings.md)**。 会社のデバイスを Defender for Business にオンボードしたら、次はセキュリティ ポリシーと設定の確認と編集です。 Defender for Business には、推奨設定を使用する事前構成済みのセキュリティ ポリシーが搭載されています。 ただし、設定はビジネス ニーズに合わせて編集できます。

   | アクション | 説明 |
   |:---|:---|
   | [セキュリティ ポリシーとデバイスを管理する場所の選択](mdb-configure-security-settings.md#choose-where-to-manage-security-policies-and-devices)。 | [簡易構成プロセス](mdb-simplified-configuration.md)を選択した場合、Microsoft 365 Defender ポータルでセキュリティ ポリシーを表示および管理できます ([https://security.microsoft.com](https://security.microsoft.com))。 ただし、このオプションに限定されるわけではありません。 [Intune](/mem/intune/protect/) を使用している場合は、引き続き Microsoft エンドポイント マネージャー管理センターを使用して、セキュリティ ポリシーとデバイスを管理できます。 |
   | [次世代の保護ポリシーの表示または編集](mdb-configure-security-settings.md#view-or-edit-your-next-generation-protection-policies)。 | 次世代の保護設定には、リアルタイム保護、事前ブロック、ネットワーク保護、望ましくない可能性のあるアプリに対して実行するアクション、ウイルス対策のスケジュール スキャンが含まれます。  |
   | [ファイアウォール ポリシーの表示または編集](mdb-configure-security-settings.md#view-or-edit-your-firewall-policies-and-custom-rules)。 | ファイアウォール保護は、会社のデバイスで送受信できるネットワーク トラフィックを指定します。 [カスタム ルール](mdb-custom-rules-firewall.md)を使用して、ファイアウォール ポリシーの例外を定義できます。 |
   | [Web コンテンツ フィルターの設定](mdb-configure-security-settings.md#set-up-web-content-filtering)。 | Web コンテンツ フィルターを使用すると、セキュリティ チームが成人向けコンテンツ、高帯域幅、法的責任、娯楽、未分類など、コンテンツの分類に基づき Web サイトへのアクセスを追跡および規制できます。 |
   | [高度な機能の設定の確認](mdb-configure-security-settings.md#review-settings-for-advanced-features)。 | Defender for Business では、セキュリティ機能が推奨設定に事前構成されています。 これらの設定を確認し、ビジネス ニーズに合わせて編集することができます。 <br/><br/>高度な機能の設定にアクセスするには、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で、**設定** > **エンドポイント** > **全般** > **高度な機能** の順に移動します。 |
   | Microsoft 365 Defender ポータルで、[他の設定を表示および編集](mdb-configure-security-settings.md#access-your-settings-in-the-microsoft-365-defender-portal)する。 | Defender for Business には、デバイスに適用されるセキュリティ ポリシーに加え、他にも表示および編集できる設定があります。 たとえば、使用するタイム ゾーンを指定したり、デバイスをオンボード (またはオフボード) したりできます。 |

## <a name="start-using-defender-for-business"></a>Defender for Business の使用を開始する

今後 30 日間、ぜひ次のセクションに記載されている新しいセキュリティ機能をお試しください。

- [脅威と脆弱性の管理ダッシュボードの使用](#use-the-threat--vulnerability-management-dashboard) 
- [検出された脅威の表示と対応](#view-and-respond-to-detected-threats)
- [セキュリティ ポリシーの確認](#review-security-policies)
- [継続的なセキュリティ管理のための準備](#prepare-for-ongoing-security-management)

### <a name="use-the-threat--vulnerability-management-dashboard"></a>脅威と脆弱性の管理ダッシュボードの使用

Defender for Business には、セキュリティ チームの時間と労力を節約するように設計された、脅威と脆弱性の管理ダッシュボードが搭載されています。 [脅威と脆弱性の管理ダッシュボードの使用](mdb-view-tvm-dashboard.md)。

- 組織のデバイスに関連付けられている暴露スコアを表示します。
- デバイスとの通信の障害に対処する、ファイアウォール保護を有効にする、Microsoft Defender のウイルス対策定義を更新するなど、セキュリティに関する最も重要な推奨事項を表示します。
- 検疫に送られたファイルや、デバイスに発見された脆弱性など、修復アクティビティを表示します。

### <a name="view-and-respond-to-detected-threats"></a>検出された脅威を表示して対応する

脅威が検出されアラートがトリガーされると、インシデントが作成されます。 組織のセキュリティ チームは、Microsoft 365 Defender ポータルでインシデントを表示および管理できます。 [検出された脅威の表示と対応](mdb-view-manage-incidents.md)。 

- [インシデントの表示と管理](mdb-view-manage-incidents.md)。
- [脅威への対応と軽減](mdb-respond-mitigate-threats.md)。
- [アクション センターでの仲介アクションの表示](mdb-review-remediation-actions.md)。
- [レポートの表示と使用](mdb-reports.md)。

### <a name="review-security-policies"></a>セキュリティ ポリシーの確認

Defender for Business では、デバイスに適用されるポリシーを使用してセキュリティ設定を構成します。 Defender for Business には、オンボード後すぐに会社のデバイスを保護し、ID、デバイス、アプリケーション、ドキュメントのセキュリティの脅威から組織を守るための、事前構成済みポリシーが搭載されています。 [セキュリティ ポリシーを確認する](mdb-view-edit-create-policies.md)。

- [既定のポリシーについて学ぶ](mdb-view-edit-create-policies.md#default-policies-in-defender-for-business)。
- [既存のポリシーを表示する](mdb-view-edit-create-policies.md#view-your-existing-policies)。
- [ポリシー センターについて理解する](mdb-policy-order.md)。 
- [次世代の構成について理解する](mdb-next-gen-configuration-settings.md)。
- [既定のファイアウォール設定を確認する](mdb-firewall.md#default-firewall-settings-in-defender-for-business)。
- [構成可能なファイアウォール設定について理解する](mdb-firewall.md#firewall-settings-you-can-configure-in-defender-for-business)。
- [Web コンテンツ フィルターを設定する](mdb-configure-security-settings.md#set-up-web-content-filtering)。 Web コンテンツ フィルターを使用すると、セキュリティ チームがコンテンツの分類に基づき Web サイトへのアクセスを追跡および規制できます。 既定では有効になっていないため、組織でこの機能を使う場合は設定する必要があります。
  
### <a name="prepare-for-ongoing-security-management"></a>継続的なセキュリティ管理のための準備

デバイスの脅威の検出、新しいデバイスの追加、従業員の組織への参加または退職など、新しいセキュリティ イベントの際にはセキュリティの管理が必要となります。 Defender for Business には、デバイスのセキュリティを管理するためのさまざまな方法があります。

- [オンボードされたデバイスのリストを表示](mdb-manage-devices.md#view-the-list-of-onboarded-devices)して、リスク レベル、露出レベル、正常性状態を確認します。
- 脅威が検出された[デバイスで対策を行う](mdb-manage-devices.md#take-action-on-a-device-that-has-threat-detections)。
- [デバイスを Defender for Business にオンボードする](mdb-manage-devices.md#onboard-a-device)。
- [Defender for Business からデバイスをオフボードする](mdb-manage-devices.md#offboard-a-device)。

## <a name="additional-resources"></a>その他のリソース

- [Defender for Business の概要](mdb-overview.md)
- [Defender for Business のチュートリアルとシミュレーション](mdb-tutorials.md)
- [ビデオ: 中小企業向けのエンタープライズ グレードの保護](https://youtu.be/umhUNzMqZto)
- [Defender for Business を取得する](get-defender-business.md)
