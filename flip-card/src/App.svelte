<script>
  import FlipCard from "./components/FlipCard.svelte";
  import { Col, Container, Row } from "sveltestrap";
  import * as dataText from "./data/data.json";
  let textBundle = dataText.default;


</script>

<svelte:head>
  <link
    rel="stylesheet"
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css"
  />
</svelte:head>

<Container>
  <Row>
    {#each textBundle as sideCard}
      <Col>
      
        <FlipCard
          sideCardText={sideCard.sideCardText}
          backCardText={sideCard.backCardText}
          src={sideCard.Logo}
        />
      </Col>
    {/each}
  </Row>
</Container>
