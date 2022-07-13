---
title: Microsoft Defender for Office 365のアーキテクチャ要件と計画の概念を確認する
description: Microsoft 365 DefenderのMicrosoft Defender for Office 365の技術図は、試用版ラボまたはパイロット環境を構築する前に、Microsoft 365 の ID を理解するのに役立ちます。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1002b03a0ebb3940d544343476045d52e8209273
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66749948"
---
# <a name="review-microsoft-defender-for-office-365-architecture-requirements-and-key-concepts"></a>Microsoft Defender for Office 365アーキテクチャの要件と主要な概念を確認する


**適用対象:**
- Microsoft 365 Defender

この記事は、Microsoft Defender for Office 365の評価環境を設定する手順 [1/3](eval-defender-office-365-overview.md) です。 このプロセスの詳細については、 [概要に](eval-defender-office-365-overview.md)関する記事を参照してください。

Defender for Office 365を有効にする前に、アーキテクチャを理解し、要件を満たすことができることを確認してください。 この記事では、アーキテクチャ、主要な概念、およびExchange Online環境で満たす必要がある前提条件について説明します。

## <a name="understand-the-architecture"></a>アーキテクチャを理解する

次の図は、サードパーティの SMTP ゲートウェイやオンプレミス統合を含めることができる Microsoft Defender for Office のベースライン アーキテクチャを示しています。 ハイブリッド共存シナリオ (つまり、運用メールボックスはオンプレミスとオンラインの両方) では、より複雑な構成が必要であり、この記事や評価ガイダンスでは取り上げられません。

:::image type="content" source="../../media/defender/m365-defender-office-architecture.png" alt-text="Microsoft Defender for Office 365のアーキテクチャ" lightbox="../../media/defender/m365-defender-office-architecture.png":::

次の表では、この図について説明します。

|コールアウト  |説明  |
|---------|---------|
|1     | 外部送信者のホスト サーバーは、通常、MX レコードのパブリック DNS ルックアップを実行します。これにより、ターゲット サーバーはメッセージを中継できます。  この紹介は、直接Exchange Online (EXO) か、EXO に対してリレーするように構成された SMTP ゲートウェイのいずれかです。  |
|2     | Exchange Online Protectionは、受信接続をネゴシエートして検証し、メッセージ ヘッダーとコンテンツを調べて、必要な追加のポリシー、タグ付け、または処理を決定します。  |
|3     | Exchange Onlineは、Microsoft Defender for Office 365と統合して、より高度な脅威の保護、軽減、修復を提供します。 |
|4     | 悪意のあるメッセージ、ブロックされたメッセージ、または検疫されていないメッセージは、迷惑メール、メールボックス ルール、またはその他の設定に関連するユーザー設定が評価およびトリガーされる EXO で受信者に処理および配信されます。 |
|5     | Azure AD Connect を使用してオンプレミスの Active Directoryとの統合を有効にし、メールが有効なオブジェクトとアカウントを Azure Active Directory と同期してプロビジョニングし、最終的にExchange Onlineできます。 |
|6      | オンプレミス環境を統合する場合は、Exchange サーバーを使用して、メール関連の属性、設定、構成の管理と管理をサポートすることをお勧めします。 |
|7      | Microsoft Defender for Office 365は、拡張検出と応答 (XDR) のためにMicrosoft 365 Defenderにシグナルを共有します。|

オンプレミス統合は一般的ですが省略可能です。 環境がクラウド専用の場合は、このガイダンスも役立つでしょう。

## <a name="understand-key-concepts"></a>主要な概念を理解する

次の表では、MDO を評価、構成、デプロイするときに理解するために重要な重要な概念を示します。


|概念  |説明 |詳細情報  |
|---------|---------|---------|
|Exchange Online Protection      |    Exchange Online Protection (EOP) は、スパムやマルウェアの電子メールから組織を保護するのに役立つクラウドベースのフィルター サービスです。 EOP は、Exchange Onlineを含むすべての Microsoft 365 ライセンスに含まれています。     |   [Exchange Online Protection の概要](../office-365-security/exchange-online-protection-overview.md)      |
|マルウェア対策保護     |    EXO 内のメールボックスを持つ組織は、マルウェアから自動的に保護されます。     |  [EOP のマルウェア対策保護](../office-365-security/anti-malware-protection.md)       |
|スパム対策保護     |   EXO 内のメールボックスを持つ組織は、迷惑メールやスパム ポリシーから自動的に保護されます。      |  [EOP のスパム対策保護](../office-365-security/anti-spam-protection.md)       |
|フィッシング対策保護 |  MDO は、スピア フィッシング、ホアリング、ランサムウェア、その他の悪意のあるアクティビティに関連する、より高度なフィッシング対策保護を提供します。   | [Microsoft Defender for Office 365での追加のフィッシング対策保護](../office-365-security/anti-phishing-protection.md)   |
|スプーフィング対策保護     |   EOP には、スプーフィングされた (偽造された) 送信者から組織を保護するのに役立つ機能が含まれています。      |   [EOP のスプーフィング対策保護](../office-365-security/anti-spoofing-protection.md)      |
|安全な添付ファイル     |   安全な添付ファイルは、仮想環境を使用して、電子メール メッセージの添付ファイルを配信する前に確認し、"爆発" することで、保護の追加レイヤーを提供します。      |   [Microsoft Defender for Office 365の安全な添付ファイル](../office-365-security/safe-attachments.md)      |
|SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル     |    さらに、SharePoint、OneDrive、および Microsoft Teams 用の安全な添付ファイルは、クラウド ストレージ リポジトリにアップロードされたファイルに対する保護の追加レイヤーを提供します。     |  [SharePoint、OneDrive、Microsoft Teams 用の安全な添付ファイル](../office-365-security/mdo-for-spo-odb-and-teams.md)       |
|安全なリンク     | セーフ リンクは、受信電子メール メッセージ内で URL スキャンと書き換えを提供し、配信またはクリックする前にそれらのリンクの検証を提供する機能です。        |   [Microsoft Defender for Office 365 の安全なリンク](../office-365-security/safe-links.md)      |
|    |         |         |

Microsoft Defender for Office に含まれる機能の詳細については、[サービスの説明Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)参照してください。

## <a name="review-architecture-requirements"></a>アーキテクチャ要件を確認する
MDO の評価または運用パイロットの成功は、次の前提条件を前提としています。
- 現在、すべての受信者メールボックスがExchange Onlineされています。
- パブリック MX レコードは EOP またはサードパーティの SMTP ゲートウェイに直接解決され、受信外部メールが EOP に直接リレーされます。
- プライマリ電子メール ドメインは、Exchange Onlineで *権限のある* ものとして構成されます。
- 必要に応じて *、ディレクトリ ベースのエッジ ブロック* (DBEB) を正常にデプロイして構成しました。 詳細については、「 [Directory-Based エッジ ブロックを使用して無効な受信者に送信されたメッセージを拒否する」を](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)参照してください。

> [!IMPORTANT]
> これらの要件が適用されない場合、またはハイブリッド共存シナリオにまだある場合、Microsoft Defender for Office 365評価では、このガイダンスで完全に説明されていないより複雑な構成または高度な構成が必要になる場合があります。

## <a name="siem-integration"></a>SIEM 統合

Microsoft Defender for Office 365を Microsoft Sentinel と統合して、組織全体のセキュリティ イベントをより包括的に分析し、効果的かつ迅速な対応のためにプレイブックを構築できます。 詳細については、「[Microsoft Defender for Office 365からアラートを接続](/azure/sentinel/connect-office-365-advanced-threat-protection)する」を参照してください。

Microsoft Defender for Office 365は、[Office 365 アクティビティ管理 API](/office/office-365-management-api/office-365-management-activity-api-reference) を使用して、他のセキュリティ情報およびイベント管理 (SIEM) ソリューションに統合することもできます。

## <a name="next-steps"></a>次の手順

手順 2/3: [評価環境のMicrosoft Defender for Office 365を有効にする](eval-defender-office-365-enable-eval.md)

[Microsoft Defender for Office 365の評価](eval-defender-office-365-overview.md)の概要に戻る

[評価とパイロットのMicrosoft 365 Defender](eval-overview.md)の概要に戻る 
