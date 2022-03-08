---
title: '手順 3: ハイブリッド ワーカーのためのセキュリティとコンプライアンスの展開'
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Microsoft 365 のセキュリティ センターとコンプライアンスのサービスを使用して、ハイブリッド ワーカー向けにご使用のアプリケーション、データ、およびデバイスを保護します。
ms.openlocfilehash: 5ae369ffa41444e0cd2d3c6d28be470ede170b01
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314057"
---
# <a name="step-3-deploy-security-and-compliance-for-hybrid-workers"></a>手順 3: ハイブリッド ワーカーのためのセキュリティとコンプライアンスの展開

ハイブリッド ワーカーの中にはオフィスを利用することが一切ない人や、利用頻度が低い人がいますが、セキュリティとコンプライアンスは、全体的なソリューションにおける重要な部分を占めています。 それらのリモート ワーカーのコミュニケーションが組織のイントラネットに限定されることはなく、すべてインターネットを介して行われます。

サイバーセキュリティのリスクを低減し、内部ポリシーやデータ規制へのコンプライアンスを管理しながら生産性を維持するために、お客様や作業者ができることがあります。

リモート ワークには、次のセキュリティやコンプライアンスの要素が必要です。

- Microsoft Teams などの、ハイブリッド ワーカーが使用する生産性アプリに対する制御されたアクセス
- チャットの会話や共有ファイルなど、ハイブリッド ワーカーが作成して使用するデータに対する制御されたアクセスや保護
- Windows 11 または 10 デバイスのマルウェアやその他の種類のサイバー攻撃からの保護
- 秘密度や保護のレベルに応じた一貫性のあるラベル付けを使用したメール、ファイル、サイトの保護
- 情報の漏洩の防止
- 地域のデータ規制への準拠

ハイブリッド ワーカーにセキュリティとコンプライアンス サービスを提供する Microsoft 365 の機能は次のとおりです。

:::image type="content" source="../media/empower-people-to-work-remotely/remote-workers-security-compliance-grid.png" alt-text="これらの Microsoft 365 サービスを使用して、セキュリティによる保護とコンプライアンスを維持します" lightbox="../media/empower-people-to-work-remotely/remote-workers-security-compliance-grid.png":::

## <a name="security"></a>セキュリティ

Microsoft 365 のこれらのセキュリティ機能を使用して、アプリケーションやデータを保護します。

|機能|なぜそれが必要なのか|ライセンス|
|---|---|---|
|Microsoft Defender for Office 365|メール メッセージ、Office ドキュメント、共同作業のツールなど、Microsoft 365 のアプリやデータを攻撃から保護します。 <p> Microsoft Defender for Office 365 は、セキュリティ リスクの検出、調査、修復のためにアプリからのシグナルを収集して分析し、電子メール メッセージ、リンク (URL)、コラボレーション ツールによってもたらされる悪意のある脅威から組織を保護します。また、標準および厳格なセキュリティ体制のための自動化されたテナント構成評価と構成ツールも提供します。|Microsoft 365 E3 または E5|
|マルウェア対策|Microsoft Defender ウイルス対策と Device Guard は、デバイス ベースのマルウェア対策を提供します。 <p> SharePoint Online では、既知のマルウェアについてファイル アップロードを自動的にスキャンします。 <p> Exchange Online Protection (EOP) は、クラウド メールボックスをセキュリティで保護します。|Microsoft 365 E3 または E5|
|Microsoft Defender for Endpoint|サイバー攻撃の脅威やデータ侵害から組織のデバイスを保護し、高度な脅威を検出し、調査し、それらに対応します。|Microsoft 365 E5|
|Defender for Cloud Apps|Microsoft 365 やその他の SaaS アプリなどのクラウドベースのサービスを攻撃から保護します。|Microsoft 365 E5 または個々の Defender for Cloud Apps ライセンス|
|Azure AD Identity Protection|ID ベースのリスクを自動的に検出して修正します。 <p>リスクベースの条件付きアクセス ポリシーを作成し、危険なサインインに対して多要素認証 (MFA) を要求します。|Azure AD Premium P2 ライセンスを含む Microsoft 365 E5 または E3|
||||

最初の手順は、[Microsoft セキュア スコア](/microsoft-365/security/defender/microsoft-secure-score)について学習し、使用することです。

詳細については、「[在宅勤務をサポートするセキュリティ チームのための最も重要な 12 のタスク](../security/top-security-tasks-for-remote-work.md)」を参照してください。

Microsoft 365 全体のセキュリティ センターの詳細については、「[Microsoft 365 セキュリティ センターに関するドキュメント](/microsoft-365/security)」を参照してください。

## <a name="compliance"></a>コンプライアンス

Microsoft 365 のこれらのコンプライアンス機能を使用して、内部ポリシーや規制要件に準拠します。

|機能|なぜそれが必要なのか|ライセンス|
|---|---|---|
|秘密度ラベル|メール、ファイル、サイトに様々な保護レベルを持ったラベルを適用することで、ユーザーの生産性や共同作業機能を妨げることなく、組織のデータを分類して保護します。|Microsoft 365 E3 または E5|
|データ損失防止 (DLP)|内部や外部での個人情報を含むデータの共有などの危険な共有、偶発的な共有、不適切な共有を検出し、警告し、ブロックします。|Microsoft 365 E3 または E5|
|アプリの条件付きアクセスを制御する|機密データがユーザーの個人用デバイスでダウンロードされるのを防止します。|Microsoft 365 E3 または E5|
|データの保持ラベルとポリシー|データの保持期間や、顧客の個人データの保管についての要件などの情報ガバナンスの制御を展開し、組織のポリシーやデータ規制に準拠します。|Microsoft 365 E3 または E5|
|Office のメッセージの暗号化 (OME)|組織内外のユーザーとの間で、顧客の個人情報などの規制されたデータを含む暗号化されたメール メッセージを送受信します。|Microsoft 365 E3 または E5|
|コンプライアンス マネージャー|Microsoft Service Trust Portal のワークフローベースのリスク評価ツールを使用して、Microsoft のクラウド サービスに関連する組織の規制準拠の取り組みを管理します。|Microsoft 365 E3 または E5|
|コンプライアンス マネージャー|Microsoft 365 コンプライアンス センターで、現在のコンプライアンス構成の全体のスコアと改善のための推奨事項を確認しましょう。|Microsoft 365 E3 または E5|
|通信コンプライアンス|組織内で不適切なメッセージを検出し、取り込んで、修復処理を実行します。|コンプライアンスまたは Insider のリスク管理アドオンを備えた Microsoft 365 E5 または Microsoft 365 E3 |
|インサイダー リスク管理|組織内の悪意のある不測の活動を検出および調査し、対処します。 Microsoft 365 は、ワーカーが管理されていないデバイスを使用している場合でも、これらの種類のリスクを検出できます。|コンプライアンスまたは Insider のリスク管理アドオンを備えた Microsoft 365 E5 または Microsoft 365 E3 |
||||

詳細については、「[Microsoft 365 コンプライアンスを開始するためのクイック タスク](../compliance/compliance-quick-tasks.md)」を参照してください。

## <a name="results-of-step-3"></a>手順 3 の結果

ハイブリッド ワーカー のために、次を実装しました。

- セキュリティ
  - ハイブリッド ワーカーがコミュニケーションや共同作業を行うために使用するアプリやデータへの制御されたアクセス
  - クラウド サービスのデータ、メール、Windows 11 または 10 デバイスのマルウェアに対する保護
- コンプライアンス
  - 秘密度や保護のレベルに応じた一貫性のあるラベル付け
  - 情報漏洩を防止するためのポリシー
  - 地域のデータ規制への準拠

## <a name="next-step"></a>次の手順

[![手順 4: デバイス、PC、その他のエンドポイントを管理する。](../media/empower-people-to-work-remotely/remote-workers-step-grid-4.png)](empower-people-to-work-remotely-manage-endpoints.md)

[手順 4](empower-people-to-work-remotely-manage-endpoints.md) に進み、デバイス、PC、その他のエンドポイントを管理します。
